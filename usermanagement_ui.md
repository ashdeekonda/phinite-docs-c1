# User Management (workspace UI)

Source of truth for this overview: Phinite Flow Gen frontend (`flow-gen-frontend`), primarily `src/app/[orgName]/workspace/[workspaceId]/users/page.tsx`, `src/services/api/UserService.ts`, and sidebar / permission wiring.

Optional Mintlify frontmatter (adapt paths and grouping when you add the page to `docs.json`):

```yaml
---
title: 'User management'
description: 'Invite teammates, assign workspace roles, and control access from the workspace Users page.'
icon: 'users'
---
```

## What it is

The **Users** screen is workspace-scoped **user management**: view people who can access the workspace, invite or link existing accounts, change **workspace roles**, optionally edit display names, remove workspace access, and resend activation email for inactive accounts.

In-app help tooltip (shown next to the page title):

> Manage workspace users, their access permissions, and roles. Invite new users, update access levels, and control who can view or modify different parts of your workspace. Use the search to find specific users, and click on user actions to edit permissions or remove access.

## How to open it

1. Select your organization from the URL segment after the host (`/[orgName]/...`).
2. Open a workspace (`/workspace/[workspaceId]/...`).
3. In the left sidebar under the user/account section, choose **Users** (route suffix `users`).

**Full path pattern**

`/[orgName]/workspace/[workspaceId]/users`

The sidebar item requires permission `workspace.sidebar.users`. If that permission is missing, **Users** does not appear in the navigation.

## Permissions that gate the UI

Page behavior is driven by the `workspace.users` permission module (see `routeModuleMapper.ts`: paths under `/workspace/.../users` map to `workspace.users`).

| Permission | Effect in the UI |
|------------|------------------|
| `workspace.users.read` | Required to load the table. Without it: **Access Denied** — "You don't have permission to view users." |
| `workspace.users.create` | Shows **+ New User** and allows opening the invite / add drawer. |
| `workspace.users.update` | Allows **Edit Access**, **Edit user details** (for workspace owner row), **Resend Email** (when account inactive), and confirming access updates. |
| `workspace.users.delete` | Allows **Remove User** from the row menu. |

**Super admin shortcut:** Users whose effective role is `super_admin` or `superadmin` are treated as having all permissions (`usePermissions` hook), regardless of the permission map.

**Loading:** Until permissions finish loading _and_ `workspace.users.read` exists in the permission map, the page shows a spinner (it does not flash "Access denied" prematurely).

## What you see on the page

### Header

- **Title:** “Users” with a count of users (stable during sorts; search uses cached totals where applicable).
- **Search:** Placeholder **Search user**. Search is debounced (~300 ms). When searching, requests include `workspaceid` so results are scoped to the current workspace.
- **New User:** Visible only with `workspace.users.create`.

### Table

Implemented as a sortable **Data Table** with server-backed pagination (“load more” when scrolling near the bottom, 20 rows per page).

**Columns (conceptual)**

- **Name** — avatar + display name (sortable).
- **Email Address** (sortable).
- **Workspace Role** — resolved from the user’s organization record for the current org and workspace (`accessPermissions` entry for `workspaceId`, otherwise org-level `role` / `accountType`, else **No access**).
- **Actions** — contextual (see below).

The **logged-in user** (“main” workspace user from `localStorage` `userid`) is handled specially: when not searching, that user may be surfaced as a distinct row pattern; actions for that row are limited (see Actions).

### Sorting

Column sort triggers a refetch with `sort` query like `name:asc` or `name:desc` passed to `GET /user_V2`.

## Workspace roles shown in selectors

When **adding** a user or **editing workspace access**, the selectable roles in the UI are:

- **Admin**
- **QA**
- **Developer**

(Defined in the “Add User to Workspace” role menu and **Edit Workspace Access** modal.)

**Note:** The table can still display other role strings returned by the API for existing users—for example **SuperAdmin** rows get **no row action menu**. The edit-access dialog initializes the selected role from the API (`viewer` is used as a fallback string if none is found), while the dropdown only lists Admin / QA / Developer—product/docs may want to call out syncing with backend enums.

**SuperAdmin in API payloads:** Code paths exist for invitations where `SuperAdmin` would mean `accountType: "SuperAdmin"`, `accessLevel: "all"`, and empty `accessPermissions`; the visible role dropdown today only offers Admin / QA / Developer.

## Actions per row

### Workspace “main” user (matches stored `userid`)

- If permitted (`workspace.users.update`): **Edit user details** (pencil). Opens a **drawer** to change **full name** only (`PUT /user/{userId}` with `{ name }`). Updating your own name also refreshes local display name storage (`userName` / `name`) and emits a `userNameUpdated` browser event.

### Other users — overflow menu (`⋮`)

- **Resend Email** — Only if `userAccountActiveStatus === false` **and** `workspace.users.update`. Calls `POST /user/resend-account-activation/{orgid}/{workspaceid}/{userid}`. Toast: success **Email sent** or error variant.
- **Edit Access** — Requires `workspace.users.update`. Opens **Edit Workspace Access** modal; confirm runs **Update Access** → `PUT` user/org access (`updateUserAccess` with `updateType: "updateworkspace"`).
- **Remove User** — Requires `workspace.users.delete`. Opens confirmation modal; confirm removes workspace access (`updateUserAccess` with `updateType: "removeworkspace"`). If this was the user’s **only** workspace permission entry, request type may switch to **`remove`** instead of **`update`** (frontend logic compares access permission count).

**SuperAdmin** (workspace role resolves to SuperAdmin): **no actions** menu is shown.

## Add User to Workspace (+ New User)

Drawer title: **Add User to Workspace**. Fields:

1. **Email Address** — validated format; cannot be your own email; may trigger lookup among org users (`newUserAllExistingUsers` cache from org listing).
2. **Full Name** — required with email for net-new invitations.
3. **User Role** — Admin / QA / Developer.

Footer hint: **User will be sent an invite email**

Primary button label varies:

| Scenario | Button | Behavior |
|---------|--------|----------|
| Brand-new email (no conflicting match) | **Add User** → runs `handleNewUserCheck`; if no exact email match among loaded users → `handleNewUserAdd` — `POST /user/create-user/{orgid}` with generated random password plus `accessPermissions: [{ workspaceid, role }]` |
| Existing org member, **not** yet on this workspace | **Update User** — `PUT` access with `updateType: "newworkspace"` |
| Existing user from another org | **Add User** — `PUT` with `type: "add"` and `updateType: "addusertoorganization"` |

**Blocked cases (examples)**

- Attempting to add your own email: validation / tooltip — cannot add logged-in user.
- User already in workspace: toast **User already exists in the workspace.**

On success, analytics event `team_member_invited` is emitted (Mixpanel) with workspace id, invitee email, invitee role, and inviter fields from `localStorage`.

## Removing access vs deleting an account

The **Remove User** flow **removes the user’s access to this workspace** (updates `accessPermissions`). It does not necessarily imply full account deletion; semantics are enforced by backend `PUT /user/organization/{type}/{userId}/{orgid}`.

## APIs used (developer reference)

| Operation | Endpoint (from `UserService`) |
|-----------|--------------------------------|
| Paginated user list | `GET /user_V2` with `orgid`, `page`, `limit`, `sort`, optional `name`, optional `workspaceid` |
| Create / invite user | `POST /user/create-user/{orgid}` |
| Update display name | `PUT /user/{userId}` |
| Update org/workspace access | `PUT /user/organization/{type}/{userId}/{orgid}` with constructed `accountType`, `accessLevel`, `accessPermissions` |
| Resend activation | `POST /user/resend-account-activation/{orgid}/{workspaceid}/{userid}` |
| Search by email (used in flows elsewhere) | `GET /user/search-by-email?email=` |
| Org-scoped legacy list | `GET /user?orgid=` |

## Suggested Mintlify sections

When turning this file into `.mdx`, consider:

1. **Overview** — what Users is for + link to workspaces / org concepts.
2. **Roles** — table mapping Admin / QA / Developer to capabilities (exact matrix may live in backend / security docs if not in UI).
3. **Inviting and adding** — net-new vs existing org vs cross-org.
4. **Changing access and removing users** — with caution callout for SuperAdmin / owner rows.
5. **Troubleshooting** — activation email, permission denied, “already in workspace.”

## Related UI copy

- Access denied: **You don't have permission to view users.**
- Empty state heading: **No Users Found** (with supporting text from the table empty message in code).
- Successful access update toast: **User workspace access has been updated successfully.**

---

*Generated from frontend implementation; behavior should be verified against the live API and your organization’s permission configuration.*
