---
title: "Managing Model Keys"
description: "Add, edit, and set default LLM provider credentials on the workspace Model Keys page."
icon: "key"
---

The **Model Keys** page is where you store and manage the provider credentials your workspace uses for inference. Keys you add here become available in **Change model** on any agent node in Graph Studio.

## Prerequisites

Before you manage Model Keys:

- Sign in to the correct organisation and workspace.
- Confirm BYOK is enabled on your plan. See [BYOK overview — Access requirements](/byok-v2/overview#access-requirements).
- Hold Model Keys read permission to view the page. Creating or editing keys requires create and update permissions.

The legacy URL `/product-api` redirects to **Model Keys**.

## Open Model Keys

1. Sign in to Phinite and select your workspace.
2. In the sidebar, click **Model Keys**.

Route: `/{organisation}/workspace/{workspaceId}/model-key`

![Model Keys page header showing key count, Search keys, Default Model, and + New Key](/images/byok/model-keys-header.png)

The header shows **Model Keys**, a count of saved keys, **Search keys** to filter the list, **Default Model** to set the workspace default, and **+ New Key** to add a credential. The info icon opens the **Model keys (BYOK — bring your own key)** tooltip with in-product examples.

## Phinite Key card

The first card is always **Phinite Key** with a **Built-in** badge. The credential line is masked—you do not enter a secret here.

![Phinite Key card with Built-in badge and Make it Default button](/images/byok/phinite-key-card.png)

Click **Make it Default** to set Phinite Key as the workspace default. The button shows **Saving…** while the request runs. When Phinite Key is already default, the button is disabled and the tooltip reads **Phinite is already the default key**.

## Custom key cards

Each provider credential you add appears as its own card.

![Custom provider key card showing provider label, masked secret, and action icons](/images/byok/custom-key-card.png)

The card shows the key name, the provider identifier in uppercase (with **(default)** when it is the workspace default), and a masked secret line. Use the icons on the card to **View key details**, **Edit key**, or **Copy Product API key to clipboard**. A successful copy shows a **Copied!** toast; a failure shows **Failed to copy**.

<Warning>
Treat Model Keys like production passwords. Restrict view and copy permissions to roles that need them.
</Warning>

## Change the workspace default

1. Click **Default Model** in the page header.
2. Select **Phinite Key** or a custom key from the dropdown.
3. Wait for **Updating…** to complete.

![Default Model dropdown open with Phinite Key and custom keys listed](/images/byok/default-model-dropdown.png)

Selecting **Phinite Key** sets the platform `phinite-provider` as default. Selecting a custom key sets that record as the workspace default. If two keys share the same name, the dropdown adds a short suffix from the key id to distinguish them.

## Add a Model Provider Key

Click **+ New Key**. The drawer title is **Add a Model Provider Key**.

![Add a Model Provider Key drawer with Name, Select Provider, and credential fields](/images/byok/add-key-drawer-workspace.png)

<Steps>
<Step title="Name the key">
Enter **Name of the Key**—for example, `production-vertex`. You cannot rename a key after you create it.
</Step>
<Step title="Select Provider">
Choose a provider from **Select Provider**. The field shows **Loading providers…** while the catalog loads. Options come from your workspace model catalog.
</Step>
<Step title="Enter credentials">
Complete the credential fields for that provider, such as **API Key** or Vertex service-account fields. Use **Show** and **Hide** to toggle secret visibility. If no fields are required, the drawer shows: *No BYOK fields are required for the selected provider.*
</Step>
<Step title="Set as default (optional)">
Enable **Make Default Provider+Key for future** to make this key the workspace default after creation. When checked, the drawer shows: *This action will override any other previous defaults.*
</Step>
<Step title="Create">
Click **Create**. The button shows **Creating...** while Phinite encrypts and stores the credential. There is no **Test** button on this drawer.
</Step>
</Steps>

<Note>
To validate a credential before publishing agent graphs, add and test the key from Graph Studio instead. See [BYOK in Graph Studio — Add and test a key](/byok-v2/graph-studio-byok#add-and-test-a-key-from-graph-studio).
</Note>

## View or edit a key

- **View key details** opens **View Model Provider Key** in read-only mode. Close with **Close**.
- **Edit key** opens **Edit a Model Provider Key**. Update credential fields only—**Name of the Key** and **Select Provider** are read-only on edit. Save with **Update** (**Updating...** while saving).

## Providers in the catalog

**Select Provider** is authoritative for your workspace. Common identifiers:

| Provider id | Credential type |
| --- | --- |
| `azure` | API key |
| `geminivertex` | Google Cloud service account fields |
| `claudevertex` | Google Cloud service account fields |
| `gmicloud` | API key |

Your workspace may show additional providers based on your catalog configuration.

## Errors and limits

| Message | What to do |
| --- | --- |
| **Access Denied** — *You don't have permission to view Product API keys.* | Request Model Keys read access from an admin. |
| **Could not load BYOK keys:** | Retry. Check network and workspace permissions. |
| **No matching keys. Try another search.** | Clear or change the **Search keys** value. |
| **Loading model keys…** | Wait for the initial page load to complete. |

Key **deletion** is not available in the product UI or API gateway at this time.

## Related pages

<CardGroup cols={2}>
<Card title="BYOK in Graph Studio" href="/byok-v2/graph-studio-byok" icon="diagram-project">
Configure **Change model** and test credentials on the canvas.
</Card>
<Card title="API & permissions" href="/byok-v2/api-and-permissions" icon="plug">
`/byok` endpoints and RBAC requirements.
</Card>
<Card title="Workspace Overview" href="/workspaces/workspace-overview" icon="grid">
Workspace structure and API Keys.
</Card>
</CardGroup>
