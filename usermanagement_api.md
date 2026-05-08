# User management (API reference)

Companion to `usermanagement_ui.md`: describes the authenticated REST surface the Flow Gen workspace **Users** experience calls against the Phinite API server (`api-server-2`). All routes below assume the app mounts user routers behind **Bearer JWT** (`authenticateToken` on `/user` and `/user_V2`).

Optional Mintlify frontmatter when you fold this into the docs site:

```yaml
---
title: 'User management API'
description: 'List users, invite members, update workspace access, and resend activation—aligned with workspace user management.'
icon: 'plug'
---
```

## Auth and permissions

| Concern | Detail |
|---------|--------|
| **Authentication** | `Authorization: Bearer <access_token>` on every `/user` and `/user_V2` request. |
| **Workspace users module** | Most operations use `checkAccess("workspace.users", "<action>")`: `read`, `create`, `update`. Create-user also applies subscription limits (`resolveSubscription`, `checkSubscriptionLimit("users")`). |
| **Self-service profile update** | `PUT /user/{userid}` does **not** use `workspace.users`; the path `userid` must equal the JWT subject (`req.user.id`). |

Super-admin clients may bypass permission checks on the frontend; the API still enforces `checkAccess` unless a route omits it (see **Gaps / notes**).

---

## Domain model (relevant fields)

Users are stored with `organizations[]` entries shaped like:

- `orgid` — organization id  
- `accountType` — org-level role (e.g. `SuperAdmin`, `superadmin`, `admin`, …)  
- `accessLevel` — org-level access string (required on create flows)  
- `accessPermissions[]` — workspace-scoped tuples: `{ workspaceid, role }`

Responses exclude `password`. Common flags: `userAccountActiveStatus`, `userid`, `name`, `email`, timestamps.

*(Schema reference: backend `models/Workspace/User.js`.)*

---

## Base paths

| Prefix | Router file (backend) |
|--------|----------------------|
| `/user` | `src/routes/orgLevel/workspaceLevel/user.js` |
| `/user_V2` | `src/routes/orgLevel/workspaceLevel/user_v2.js` |

---

## List users (paginated, workspace-aware)

**`GET /user_V2`**

**Permission:** `workspace.users` **read**.

**Query parameters**

| Param | Required | Notes |
|-------|----------|--------|
| `orgid` | Yes | Organization to scope the list. |
| `page` | No | Default `1`; must be ≥ 1. |
| `limit` | No | Default `10`; clamped **1–100**. |
| `sort` | No | Comma-separated `field:direction`; `direction` ∈ `asc` \| `desc`. Allowed fields: `name`, `email`, `createdAt`, `updatedAt`, `userid`. Default sort: `createdAt:desc`. |
| `workspaceid` | No | Strongly recommended for workspace UIs—see filtering behavior below. |
| `role` | No | Used when expanding SuperAdmin workspace rows (defaults to `"SuperAdmin"` in that path). |
| `name` | No | Case-insensitive partial match on **name or email**. |

**Filtering semantics (important)**

- **With `workspaceid`:** returns users who are **SuperAdmin/SuperAdmin (case variants) for that org** *or* have that `workspaceid` in `accessPermissions` for that org.
- **Without `workspaceid`:** returns **only SuperAdmin-class users** for that org (not all members).

**Responses**

- **200** — `{ data: User[], pagination: { currentPage, itemsPerPage, totalItems, totalPages, hasNextPage, hasPreviousPage, nextPage, previousPage, sort } }`
- **400** — e.g. missing `orgid`, invalid pagination
- **404** — requested `page` beyond last page (`type: "page_not_found"` and pagination meta)
- **500** — server error (implementation may respond with `{ message }`)

---

## Legacy org user list (unpaginated)

**`GET /user?orgid=<orgid>`**

**Permission:** `workspace.users` **read**.

Returns a **JSON array** of all users whose `organizations` includes that `orgid`, each with expanded `organizations` (org names, workspaces, roles). Not paginated; prefer `GET /user_V2` for large orgs.

---

## Search users by email

**`GET /user/search-by-email?email=<string>`**

**Permission:** `workspace.users` **read**.

**Important:** Scoped with **`organizations.orgid` matching `req.user.orgid` from the token** (not a query param). Email match is regex, case-insensitive.

---

## Get one user

**`GET /user/:userid`**

**Permission:** `workspace.users` **read**.

Returns a single user document (`password` excluded). Responses may be **cached** server-side (`user_details_{userid}`).

---

## Current caller’s org and workspace tree

**`GET /user/org-list`**

**Permission:** authenticated only (no `checkAccess` guard in router).

Uses `req.user.id` as `userid` and returns an array of org summaries including `workspaceList`, `role` (`accountType`), billing hints, etc. Useful for navigation and context, separate from workspace user administration.

---

## Create user / invite / add org to existing identity

**`POST /user/create-user/:orgid`**

**Permission:** `workspace.users` **create** (plus subscription user limit enforcement).

**Body (required unless noted)**

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Display name |
| `email` | Yes | Stored lowercased |
| `password` | Yes | Hashed server-side. **Still required when the email already belongs to an existing user** (same validation gate); callers often send an unused random value, as in the workspace UI. |
| `accountType` | Yes | Org account type |
| `accessLevel` | Yes | Org access level |
| `accessPermissions` | No | Array of `{ workspaceid, role }`; defaults `[]` |

**Behavior**

- **Email not in system:** Creates user (`userAccountActiveStatus: false`), org membership, activation + verify tokens, sends **invitation** email with login/verify link.
- **Email already exists:** **Appends** a new `{ orgid, accountType, accessLevel, accessPermissions }` entry to `organizations` and notifies via **existing-user invitation** email.

**Responses**

- **200** — `{ user, message }` where `message` is `"User created successfully"` or `"Existing user new organization updated successfully"`  
- **400** — missing fields  
- **404** — org not found  
- Validation errors may come back as **404** with `Validation errors: …` per current implementation  

---

## Update profile fields (caller only)

**`PUT /user/:userid`**

**Auth:** JWT `userid` must match path `userid`; **no** `workspace.users` check.

**Body:** Partial update object (commonly `{ "name": "..." }`). Merged with `findOneAndUpdate`. Clears permission/user caches affecting that user.

**Typical errors:** `400` `"Unauthorized to update this user"`; `404` `"User not found"` or token/expiry messaging.

---

## Add / update / remove organization membership & workspace access

**`PUT /user/organization/:type/:userid/:orgid`**

**Permission:** `workspace.users` **update**.

**Path `type`** (string): **`add`**, **`update`**, or **`remove`**.

### Critical implementation detail

The handler derives **`orgid` from `req.user.orgid`**, not from the path segment. Callers should still supply a coherent URL (the frontend often echoes org id); **authorization checks use the token org** and validate the target user already has that org entry before mutation.

### Body (for `add` / `update`)

Typically includes:

- `accountType`
- `accessLevel` *(shape depends on callers; omit when only adjusting permissions)*  
- `accessPermissions`: `[{ workspaceid, role }, …]`

**`type === add`**

Appends `{ orgid, ...updates }` to `organizations`, sends invitation email to existing inbox for the add flow.

**`type === update`**

Replaces organization entry for matching token-org with `{ ...existingOrg merged with updates from body }`, especially `accessPermissions`. Server compares old vs new permissions to optionally send emails for newly added workspaces, changed roles (different template), or removed workspace rows (removed path currently does not mail from that branch—the “remove workspace” UX usually shrinks `accessPermissions`).

**`type === remove`**

Removes the **entire organization membership** (`organizations` filtered to drop that `orgid`)—not merely one workspace—and sends removal email (`sendRemoveOrganizationEmailToUser`).

Frontend “Remove user from workspace” vs “remove entire org” is implemented by comparing permission counts (see UI doc): **narrow workspace removal uses `update` with truncated `accessPermissions`**; **`remove` drops the whole org**.

---

## Resend activation / invitation email

**`POST /user/resend-account-activation/:orgid/:workspaceid/:userid`**

**Permission:** Router has **no** `checkAccess` in code—still requires valid JWT from global middleware.

Loads **Account Verify** token for `userid`. If JWT not expired, resends invitation with existing link; if expired, rotates verify token (**24h**), persists, sends new message.

**Responses:** **`200`** `{ message: "Account activation email sent successfully" }`; **`404`** if Account Verify token missing.

---

## UI ↔ API quick map

| UX flow | Primary API |
|--------|--------------|
| Paginated users table, sort, workspace scope | `GET /user_V2` |
| Invite / add workspace member | `POST /user/create-user/{orgid}` or `PUT /user/organization/update/...` with new `accessPermissions` |
| Cross-org existing user → add to org | `PUT /user/organization/add/{userid}/{orgid}` (see path note) |
| Edit display name (self row) | `PUT /user/{userid}` |
| Edit workspace role / Remove from workspace | `PUT /user/organization/update/{userid}/{orgid}` with updated `accessPermissions` |
| Remove user from entire org | `PUT /user/organization/remove/{userid}/{orgid}` |
| Resend activation | `POST /user/resend-account-activation/{orgid}/{workspaceid}/{userid}` |
| Lookup by email in org token | `GET /user/search-by-email?email=` |
| Legacy bulk list | `GET /user?orgid=` |

---

## Gaps / notes for docs and QA

1. **`PUT /user/:userid`** skips `workspace.users`—security is strictly “same as token user”; admins cannot PATCH another user’s name via this endpoint in current code.
2. **`GET /user_V2`** without `workspaceid` is **SuperAdmin-only**—easy to misuse in automation expecting “all members.”
3. **`PUT /user/organization/...`** path `:orgid` is **ignored** for business logic (`req.user.orgid` wins).
4. **Resend activation** lacks explicit `workspace.users` permission middleware—behavior should match product policy.
5. **Role strings** are not centrally enum-validated here; workspace UI restricts to Admin / QA / Developer while API payloads may surface `SuperAdmin`, `viewer`, etc.

---

## Related docs in this repo

- **UI overview:** `/Users/hansidruvan/Documents/GitHub/Phinite/docs/usermanagement_ui.md`
- **End-user guide:** `user-management/user-management.md`, `user-management/inviting-users.md`, `user-management/access-controls.md`, `user-management/user-roles.md`

---

*Sourced from `api-server-2` route implementations; verify payloads and statuses against your deployed environment and OpenAPI (`@swagger` blocks on the same route files).* 
