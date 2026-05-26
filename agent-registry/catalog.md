---
title: "Browse Agent Registry"
description: "Search organisation and catalogue agents from the Agent Registry UI."
---

## Open Agent Registry

In the workspace, open **Agent Registry** from the primary sidebar when your organisation grants **`workspace.sidebar:agent_registry`** (or legacy variant `workspace.sidebar.agent_registry`). Routes match:

- Workspace: `/{organisation}/workspace/{workspaceId}/agent-registry`
- Projects (conversational / voice placements): `/.../projects/{projectId}/agent-registry`

## Tabs you will see

| Tab | Behaviour |
| --- | ----------- |
| **Organisation** | Agents registered under your workspace’s organisation filters (see current product rules for statuses such as test vs live listings). |
| **Public** | Catalogue-style listing with **`status=live`** query semantics in the SPA. |
| **Sample** | Static demo entries loaded from **`agents.json`** in the SPA for UI exploration—not your live catalogue. |

## Search & detail

Use the search bar to narrow by agent name, summary, or team labels shown on cards. Selecting a card opens a detail view with skills, lifecycle status, visibility, and the endpoint you can copy for integrations.

Infinite scroll pagination applies to API-backed tabs (page size **`10`** in the current frontend).

Implementation reference:

- `src/app/[orgName]/workspace/[workspaceId]/agent-registry/page.tsx`
- Paginated **`GET /a2a-registry`** with `workspaceid`, `orgid`, `page`, `limit`.
