---
title: "BYOK glossary"
description: "Exact UI labels, API field names, and permission identifiers for Model Keys."
icon: "book-open"
sidebarTitle: "Glossary"
---

Use this page to find the exact product label or API field name for any BYOK concept.

## Product terms

| Term | Meaning |
| --- | --- |
| **Model Keys** | Workspace page and sidebar entry for BYOK |
| **Bring Your Own Key (BYOK)** | Using customer-provided provider credentials for inference |
| **Phinite Key** | Built-in, platform-managed credential. No secret required. |
| **Model Provider Key** | One saved credential row for a specific provider |
| **Change model** | Graph Studio modal for configuring resource, operation, model, and key on an agent node |

## Change model — UI labels

| Label | Notes |
| --- | --- |
| **Resource** | Modality dropdown: text, image, video, audio, document |
| **Operation** | Segmented control: **Generate** or **Analyze** |
| **Model** | Catalog model for the selected resource and operation |
| **Bring your own key(BYOK)** | Toggle. Note the exact casing and parentheses. |
| **Model Provider** | Provider dropdown. Visible only when BYOK is on. |
| **Select Your Key(BYOK)** | Workspace key dropdown. Visible only when BYOK is on. |
| **+ Add New Key** | Opens the studio add-key panel without closing **Change model** |
| **Cancel** / **Done** | Footer actions. The modal does not use "Save". |
| **Test** / **Testing** | Test-connection button. Studio add-key panel only—not on the workspace drawer. |

## Model Keys page — UI labels

| Label | Notes |
| --- | --- |
| **Model keys (BYOK — bring your own key)** | Info tooltip title on the sidebar item |
| **Search keys** | List filter field |
| **Default Model:** | Header dropdown for workspace default |
| **Select default model** / **Updating…** | Dropdown placeholder states |
| **+ New Key** | Primary action to open the create drawer |
| **Phinite Key** | Name of the built-in card |
| **Built-in** | Badge on the Phinite Key card |
| **Make it Default** / **Saving…** | Button to set Phinite Key as default |
| **Add a Model Provider Key** | Create drawer title |
| **Edit a Model Provider Key** | Edit drawer title |
| **View Model Provider Key** | View drawer title |
| **Name of the Key** | Key display name field |
| **Select Provider** | Provider picker in the drawer |
| **Make Default Provider+Key for future** | Checkbox to set default on save |

## API fields

Internal field names used in the API and stored on agent nodes. Prefer product labels in customer-facing content; reference these in technical integrations.

| Field | Where it appears | Meaning |
| --- | --- | --- |
| `byokid` | Agent node, published build | Reference to the workspace Model Key |
| `developMode` | Agent orchestration | `phinite` (platform key) or `self` (BYOK) |
| `isDefault` | BYOK record | Whether this key is the workspace default |
| `ownKey` | Usage event | Own-key inference; platform cost excluded from aggregation |

## Permissions

| Identifier | Layer | Controls |
| --- | --- | --- |
| `workspace.byok` | API | Access to `/byok` routes |
| `workspace.api_keys` | UI | Model Keys page: list, create, update, view, copy |
| `workspace.sidebar.api_keys` | UI | **Model Keys** sidebar entry visibility |

## Related pages

<CardGroup cols={2}>
<Card title="API & permissions" href="/byok-v2/api-and-permissions" icon="plug">
Route table and runtime resolution.
</Card>
<Card title="Access Controls" href="/user-management/access-controls" icon="shield">
Role and permission assignment.
</Card>
</CardGroup>
