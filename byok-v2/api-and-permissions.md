---
title: "BYOK API & permissions"
description: "Gateway routes, RBAC requirements, and how Phinite resolves Model Keys at runtime."
icon: "plug"
---

This page covers the API routes for Model Keys, the permissions that control access, and how the server resolves a key reference at runtime.

## Permissions

Model Keys use two separate permission modules. Align role assignments in [Access Controls](/user-management/access-controls) to ensure only trusted roles can create or view decrypted secrets.

| Layer | Permission | What it controls |
| --- | --- | --- |
| API | `workspace.byok` | Access to all `/byok` routes |
| Model Keys UI | `workspace.api_keys` | List, create, update, view, and copy keys in the product |
| Sidebar | `workspace.sidebar.api_keys` | Show **Model Keys** in the workspace sidebar |

## API routes

All routes are proxied through the API gateway to api-server-2. There is no `DELETE /byok` in the gateway at this time.

| Method | Route | Purpose |
| --- | --- | --- |
| `GET` | `/byok` | List workspace keys; values masked. Optional `?provider=` filter. |
| `GET` | `/byok/{byokid}` | Fetch one key; returns decrypted value for authorized callers. |
| `POST` | `/byok` | Create a key. Credential is encrypted before storage. |
| `PUT` | `/byok/{byokid}` | Update credentials or set `isDefault`. |
| `POST` | `/byok/test-connection` | Validate a credential against AI Core. Called by Graph Studio **Test**. |

List responses always mask the secret value. **View key details** and **Copy** in the product call `GET /byok/{byokid}` for authorized users.

## Setting the workspace default

The UI actions for setting a default map to these API calls:

- **Make it Default** on the Phinite Key card → creates or updates the platform `phinite-provider` record as default.
- **Default Model** dropdown → `PUT /byok/{byokid}` with `isDefault: true` on the selected key.
- **Make Default Provider+Key for future** on the create drawer → same flag set at `POST /byok` time.

## How the node configuration is saved

When you click **Done** in **Change model**, Graph Studio maps the modal state to the agent block:

- BYOK off → platform-managed mode, no key reference stored on the node.
- BYOK on with a key selected → your-key mode, the selected key id stored on the node.
- A new key added from the studio panel → `POST /byok` (and optional test) runs first, then the key id is stored.

At publish and runtime, the server loads the key by its stored id, decrypts it, and passes the credential to AI Core. Keep the key id stable across environments where that workspace key exists.

## Billing flag

When inference uses your Model Key, usage events can carry an own-key flag. Platform token and media cost aggregation excludes those events. Session and event volumes may still appear in observability for debugging. See [Billing with BYOK](/byok-v2/billing-and-usage).

## Related pages

<CardGroup cols={2}>
<Card title="Managing Model Keys" href="/byok-v2/managing-model-keys" icon="key">
Workspace UI for key list and drawers.
</Card>
<Card title="BYOK in Graph Studio" href="/byok-v2/graph-studio-byok" icon="diagram-project">
**Change model** and **Test** on the canvas.
</Card>
<Card title="Glossary" href="/byok-v2/glossary" icon="book-open">
UI labels and stored field names.
</Card>
</CardGroup>
