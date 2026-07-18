---
title: Agent Registry
description: Search, filter, and inspect exposed A2A agents in the workspace catalog.
---

## What this is

The **Agent Registry** is the workspace catalog of agents exposed over A2A. Each entry links an Agent Graph **Build** to an **Agent Card**, hosted URL, and deployment status (**TEST** / **LIVE**).

## Where in the product

| Surface | Path |
| --- | --- |
| Workspace sidebar | **Agent Registry** |
| URL | `/{org}/workspace/{workspaceId}/agent-registry` |
| Permissions | `workspace.sidebar.agent_registry` |

![Agent Registry](/images/v2/a2a/04-registry-catalog.png)

## Page layout

| Area | Description |
| --- | --- |
| Hero | *Find the Perfect AI Agent* — search across registry entries |
| Search | Filter by name, summary, tags |
| Filters | Visibility, deployed status, input/output MIME modes, tags |
| Detail | Skills, status, visibility, copyable endpoint |

## Filter dimensions

| Filter | Options | Matches |
| --- | --- | --- |
| **Visibility** | Public, Organisation | Agent Card visibility |
| **Deployed** | Live, Test | Build status |
| **Input / Output Mode** | MIME types | Skill compatibility |
| **Tags** | Discoverability tags | Topic / capability |

## Steps

1. Open **Agent Registry** from the workspace sidebar.
2. Search or apply filters to narrow agents.
3. Select an agent to view **Agent Card** details and hosted URL.
4. Use **TEST** URLs for validation; **LIVE** URL after [Push to Prod](/a2a/agent-card-identity).

## Related

- [Agent Card identity](/a2a/agent-card-identity)
- [A2A discovery](/a2a/discovery)
- [A2A endpoints](/a2a/endpoints)
- [Expose as A2A](/agents/expose-a2a)
