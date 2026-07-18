---
title: "TeamsTool"
description: "Microsoft Teams messaging and approval flows via Microsoft Graph."
icon: "microsoft"
---

**TeamsTool** sends Teams messages and supports approval-style flows using Azure AD application credentials.

<Card title="Predefined tools hub" icon="plug" href="/devstudio/prebuilt-tools">
  Shared connection concepts for prebuilt integrations.
</Card>

## Required configuration

| Field | Type | Notes |
| --- | --- | --- |
| `app_id` | string | Azure AD application (client) ID |
| `app_secret` | string | Client secret |
| `tenant_id` | string | Azure AD tenant ID |

## Setup

1. Register an Azure AD app with Microsoft Graph permissions for your subtools (for example `ChatMessage.Send`).
2. In Graph Studio, add **TeamsTool** on an agent node and create a connection with the three fields above.
3. Enable `send_for_approval` (or other subtools as they ship) and test in **Dev**.
4. **Save** the graph before **Build**.

## Subtools

- `send_for_approval` — post a message with variables and wait for approval (adaptive cards / notifications may be required).

<Note>
  Graph **delegated** vs **application** permissions behave differently. Match your connection type to how the Agent Graph runs (background bot vs user-delegated).
</Note>

## Related

- [Microsoft Teams channel](/channels/teams)
- [Integrations Hub — Teams](/integrations-hub/teams)
