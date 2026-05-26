---
title: "Managing Model Keys"
description: "Add and manage LLM provider credentials on the workspace Model Keys page, including the Phinite Key and custom provider keys."
icon: "key"
---

## Open Model Keys

1. Open your organisation and workspace.
2. In the sidebar, select **Model Keys**.

Route: `/{organisation}/workspace/{workspaceId}/model-key`

The legacy route `/product-api` redirects to this page.

You need read access to Model Keys to view the page. Creating or updating keys requires create and update permissions on the Model Keys module.

## Page layout

The page header includes:

- **Model Keys** and a key count
- **Search keys** to filter the list
- **Default Model** to choose the workspace default key
- **+ New Key** to add a provider key (when permitted)

### Phinite Key

The first card is always **Phinite Key**, labeled **Built-in**. It represents platform-managed inference. The value area shows a masked placeholder, not an editable secret.

Use **Make it Default** to set Phinite Key as the workspace default. The button is disabled when Phinite Key is already default.

### Custom keys

Each custom key appears as a separate card with:

- Key name
- Provider identifier (shown in uppercase), with **(default)** when that key is the workspace default
- Masked credential display
- **View**, **Edit**, and **Copy** actions when your role allows

Listed values are always masked. View and copy fetch the decrypted secret from the server for authorized users.

## Add a key

Click **+ New Key** to open **Add a Model Provider Key**.

<Steps>
<Step title="Name the key">
Enter a name in **Name of the Key** (for example `production-azure`). The name cannot be changed after creation.
</Step>
<Step title="Select a provider">
Choose a provider in **Select Provider**. Options come from the workspace model catalog. While the list loads, the field shows **Loading providers…**.
</Step>
<Step title="Enter credentials">
Complete the fields for that provider. Labels such as **API Key** or **Project Id** are generated from the provider schema. Password-style fields support **Show** and **Hide**.

If the provider requires no fields, the form shows: *No BYOK fields are required for the selected provider.*
</Step>
<Step title="Set as default (optional)">
To make this key the workspace default, enable **Make Default Provider+Key for future**. Enabling it shows a notice that previous defaults will be overridden.
</Step>
<Step title="Save">
Click **Create**. The credential is encrypted before it is stored.
</Step>
</Steps>

<Note>
The workspace drawer does not include **Test connection**. To validate credentials before publishing flows, add or test keys from Graph Studio using **+ Add New Key** in the **Change model** modal.
</Note>

## Edit or view a key

- **View Model Provider Key** — read-only details; close with **Close**.
- **Edit a Model Provider Key** — update credential fields. Name and provider cannot be changed.

## Change the workspace default

Use **Default Model** in the header to switch between Phinite Key and a custom key. If two keys share the same name, the dropdown adds a short suffix from the key id to distinguish them.

| Selection | Behavior |
| --------- | -------- |
| Phinite Key | Creates or updates the platform `phinite-provider` record as default |
| Custom key | Sets `isDefault: true` on the selected key |

## Providers

Available providers depend on your workspace catalog (`/models_V2?provider_only=true`). Common provider identifiers include:

| Provider | Credential type |
| -------- | ---------------- |
| `azure` | API key |
| `geminivertex` | Google Cloud service account fields |
| `claudevertex` | Google Cloud service account fields |
| `gmicloud` | API key |

Use the **Select Provider** dropdown in the product for the authoritative list and required fields.

## Errors and limits

| Message | Meaning |
| ------- | ------- |
| Access Denied | You lack permission to view Model Keys |
| Could not load BYOK keys | The key list failed to load; check network or permissions |
| No matching keys. Try another search. | No key matches the search filter |

Key deletion is not available in the UI at this time.

## API summary

| Method | Path | Purpose |
| ------ | ---- | ------- |
| `GET` | `/byok` | List keys (masked values) |
| `GET` | `/byok/{byokid}` | Get one key (decrypted for authorized callers) |
| `POST` | `/byok` | Create a key |
| `PUT` | `/byok/{byokid}` | Update a key or set default |

Permissions: `workspace.byok` on the API.

## Related

- [BYOK overview](/byok/overview)
- [BYOK in Graph Studio](/byok/graph-studio-byok)
- [Workspace Overview](/workspaces/workspace-overview)
