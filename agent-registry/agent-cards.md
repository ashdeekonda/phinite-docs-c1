---
title: Agent Cards & builds
description: Manage A2A registry builds per Agent Graph, compare TEST and LIVE deployments, and promote to production.
---

<Note>
  **Agent Cards** is the graph-scoped view of **A2A registry builds**. Each expose action creates a TEST row; **Push To Prod** promotes one build to LIVE per Agent Graph per workspace.
</Note>

**Agent Cards** lists **A2A registry builds** for each exposed **Agent Graph**. Inspect build history, compare **TEST** and **LIVE** deployments, and **promote** a build to production.

## Open Agent Cards

**Route:** `/{organisation}/workspace/{workspaceId}/projects/{projectId}/agent-cards`

The page appears in the **project sidebar** when **`workspace.sidebar.agent_registry`** is granted. Reach it from Graph Studio via **Deploy** → **Deploy as A2A** → **See Agent builds**, or Studio → **Agent Cards** in graph assets.

<Frame caption="Agent Cards sidebar — TEST and LIVE builds per graph">
  <img src="/images/v2/a2a/01-agent-cards-sidebar.png" alt="Agent Cards panel in Graph Studio" />
</Frame>

<Frame caption="Agent Card identity — version details for an exposed graph">
  <img src="/images/v2/a2a/03-agent-card-identity.png" alt="Agent Card identity sidebar view" />
</Frame>

## Page layout

| Element | Description |
| --- | --- |
| **Title** | **Agent Cards** with total build count |
| **Agent Graph** dropdown | Filter builds by graph (`flowid`); options from **`GET /a2a-registry?flow_list=true`** |
| **Build table** | Rows per registry build: build number, status, name, description, tools/env counts, updated date, author |
| **Push To Prod** | Promote a **TEST** build to **LIVE** |

## Build rows

Each row represents one **`POST /a2a-registry`** registration:

| Column / field | Source | Notes |
| --- | --- | --- |
| **Build number** | `build_no` | Auto-incremented per workspace + Agent Graph |
| **Status** | `test` or `live` | Badge: **TEST** or **LIVE** |
| **Name / description** | `agent_card` | Agent Card from expose wizard |
| **Tools / env** | `tool_config`, `env_variable` | Exported configuration counts |
| **Registry ID** | `a2aregistryid` | Used in TEST hosted URLs |

Builds sort by **most recently updated** first.

## TEST vs LIVE

| Status | Purpose | Hosted URL |
| --- | --- | --- |
| **Test** | Validate Agent Card, skills, and integrations | `{gateway}/api/v1/ai/a2a/{flowId}/{registryId}` |
| **Live** | Production endpoint (one LIVE per graph per workspace) | `{gateway}/api/v1/ai/a2a/{flowId}` |

See [Endpoints & lifecycle](/agent-registry/endpoints-and-lifecycle) for URL and auth details.

## Promote to production

1. Click **Push To Prod**.
2. In the modal, select the **TEST** build to promote.
3. Confirm promotion.

The app calls:

```text
PUT /api/v1/a2a-registry/{a2aregistryid}/promote-live
```

**Promotion rules:**

- The chosen build becomes **`live`**.
- Any previous **LIVE** build for the same Agent Graph in the workspace is demoted to **`test`**.
- Agent Card visibility is unchanged by promotion — only deployment status updates.

## Create a new build

New builds are created from Graph Studio:

1. Create an **Agent Build** ([Builds overview](/builds/overview)).
2. [Expose your Agent Graph](/agent-registry/expose-your-flow) via **Deploy** → **Deploy as A2A**.
3. Return to Agent Cards to compare the new **TEST** row.

## Permissions

| Action | Permission |
| --- | --- |
| View builds | `assistants.flows:read` |
| Promote to live | `assistants.flows:update` |
| Sidebar entry | `workspace.sidebar.agent_registry` |

## Related pages

<CardGroup cols={2}>
  <Card title="Expose an agent" icon="rocket" href="/agent-registry/expose-your-flow">
    Create a new TEST build and Agent Card.
  </Card>
  <Card title="Endpoints & lifecycle" icon="plug" href="/agent-registry/endpoints-and-lifecycle">
    URL patterns and API reference.
  </Card>
</CardGroup>
