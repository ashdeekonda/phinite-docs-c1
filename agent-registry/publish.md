---
title: "Publish and endpoints"
description: "Expose agent graphs as A2A agents, manage Agent Cards and builds, and understand hosted URLs, lifecycle, auth, and registry APIs."
---

<a id="expose-wizard"></a>

## Expose wizard
### Prerequisites

Before you expose an agent graph:

- **Publish** at least one version of the agent graph. See **[Agent Graph publishing](/graph-studio/publishing)**.
- Hold **Developer** role or higher for Graph Studio save/publish actions.
- Have permission to call registry APIs (`assistants.flows:create` via the gateway **`POST /a2a-registry`**).
- Run in a **local or dev** environment where **Configure Agent** is visible in Graph Studio (see **[Overview — Access and environment](/agent-registry/overview#access-and-environment)**).

Associated **tools** referenced by the graph must be **published** before you can select them in step 1 of the wizard.

### Open the expose flow

1. Open **Graph Studio** for your project.
2. Select the agent graph you want to expose.
3. In the canvas header, click **Configure Agent** (dev environments only).
4. In the **Expose as Agent** modal, review any existing test/live builds and hosted URLs.
5. Click **Create New Build** to open the **Expose as External Agent** wizard.

![Expose as Agent modal with hosted URL and Create New Build](/images/agent-registry/expose-modal.png)

The modal explains that publishing an Agent Card enables the graph as a **hosted agent** callable via the **A2A protocol**. Use **See Agent builds** to jump to **[Agent Cards](#agent-cards-and-builds)** for the project.

### Wizard steps

The wizard has three steps. Step labels in the UI:

| Step | Label | Purpose |
| ---- | ----- | ------- |
| 1 | **Agent Build Config** | Pick agent graph version and published tools |
| 2 | **Additional Config** | Optional export of tools/variables to the build |
| 3 | **Configure the Agent card** | Agent Card identity, skills, tags, visibility |

Primary actions: **Next** (steps 1–2), **Attach Agent Card** (step 3).

#### Step 1 — Agent Build Config

![Wizard step 1: Agent Build Config with graph version and tools](/images/agent-registry/wizard-step1-build-config.png)

**Confirm the Agent Config:**

- **Agent Graph** accordion — select the flow version to register (name, version number, version notes, timestamp).
- **Tools Associated** accordion — select published tool versions linked to the graph. Unpublished tools show a **Publish** action inline.

Validation requires a selected graph version. If tools exist on the graph, at least one **published** tool must be selected.

#### Step 2 — Additional Config

**Variables and Secrets:**

- Toggle **Export to build** to include predefined tools, MCP tools, or environment variables in the registry build.
- When enabled, use tabs **Predefined**, **MCP**, and **Env** and search **Search tools and variables...**
- For each exported row, provide a **description** (required).

When export is disabled, the step shows: *Enable "Export value to build" to configure additional tools and variables.*

#### Step 3 — Configure the Agent card

![Wizard step 3: Agent Card with skills, tags, and visibility](/images/agent-registry/wizard-step3-agent-card.png)

**Agent Card is the identity of your agent on the Internet:**

| Field | Notes |
| ----- | ----- |
| **Agent Name** | Read-only; derived from the agent graph name |
| **Agent Description** | Editable summary for catalog and A2A clients |
| **Skills** | Add skills with unique name, description, **Input Modes**, and **Output Modes** (MIME types) |
| **Discoverability Tags** | Tags help agents appear in search and Discovery filters |
| **Visibility & access** | **Public** — discoverable by any A2A-compatible agent or user with a valid API key. **Organisation** — visible only within your organisation |
| **Auth Schemes** | Platform default: use your Phinite organisation **API key** |
| **Refine Card** | Optional AI refinement (`refine_prompt_for: "a2a"`) to improve description and skills |

Click **Attach Agent Card** to submit. The UI calls **`POST /a2a-registry?workspaceid={workspaceId}`** with the wizard payload (`agent_card`, `flowid`, `flow_version`, `assistantid`, tools, and optional export config).

### After registration

![Success state with registry ID and hosted test URL](/images/agent-registry/expose-success.png)

On success:

- Note the **Agent Registry ID** and **hosted A2A URL** (test builds use the registry ID in the path—see **[Hosted URLs and lifecycle](#hosted-urls-and-lifecycle)**).
- The success message indicates the build is available to **Test**.
- Click **Go to Agent Registry** to open the workspace catalog.

New registrations start with deployment status **`test`**. Promote to **`live`** from **[Agent Cards and builds](#agent-cards-and-builds)** when you are ready for production routing.

<a id="agent-cards-and-builds"></a>

## Agent Cards and builds
**Agent Cards** is the project-scoped view of **A2A registry builds** for each exposed agent graph. Use it to inspect build history, compare **test** and **live** deployments, and **promote** a build to production.

![Agent Cards page with build table and Push To Prod](/images/agent-registry/publish#agent-cards-and-builds-builds.png)

### Open Agent Cards

**Route:** `/{organisation}/workspace/{workspaceId}/projects/{projectId}/agent-cards`

The page appears in the **project sidebar** for conversational and voice assistants when **`workspace.sidebar.agent_registry`** is granted (same permission as workspace **Agent Registry**). Like other registry features, it is typically visible in **local/dev** environments.

You can also reach Agent Cards from Graph Studio via **Configure Agent** → **Expose as Agent** → **See Agent builds**.

### Page layout

| Element | Description |
| ------- | ----------- |
| **Title** | **Agent Cards** with total build count |
| **Agentic graph** dropdown | Filter builds by agent graph (`flowid`); options from **`GET /a2a-registry?flow_list=true`** |
| **Build table** | Rows per registry build: build number, status, name, description, tools/env counts, updated date, author |
| **Push To Prod** | Opens promote modal to move a **test** build to **live** |

While data loads, the page shows *Loading builds...*.

### Build rows

Each row represents one **`POST /a2a-registry`** registration (one expose action). Key fields:

| Column / field | Source | Notes |
| -------------- | ------ | ----- |
| **Build number** | `build_no` | Auto-incremented per workspace + agent graph |
| **Status** | `test` or `live` | Badge: **TEST** or **LIVE** |
| **Name / description** | `agent_card` | Agent Card from expose wizard |
| **Tools / env** | `tool_config`, `env_variable` | Exported configuration counts |
| **Registry ID** | `a2aregistryid` | Used in test hosted URLs |

Builds sort by **most recently updated** first.

### Test vs live

| Status | Purpose | Hosted URL |
| ------ | ------- | ---------- |
| **Test** | Validate Agent Card, skills, and integrations before broad use | `{gateway}/api/v1/ai/a2a/{flowId}/{registryId}` |
| **Live** | Production endpoint for the agent graph (only one live row per graph per workspace) | `{gateway}/api/v1/ai/a2a/{flowId}` |

See **[Hosted URLs and lifecycle](#hosted-urls-and-lifecycle)** for URL and auth details.

### Promote to production

1. Click **Push To Prod** (tooltip: *Push the selected build to production*).
2. In the modal, select the **test** build to promote.
3. Confirm promotion.

The app calls:

```
PUT /api/v1/a2a-registry/{a2aregistryid}/promote-live
```

**Promotion rules:**

- The chosen build becomes **`live`**.
- Any previous **live** build for the same agent graph in the workspace is demoted to **`test`**.
- Visibility on the Agent Card is unchanged by promotion—only deployment status updates.

After promotion, refresh the table and verify the **live** hosted URL on the build row or in **[Browse the catalog](/agent-registry/compose#catalog)**.

### Create a new build

New builds are created from Graph Studio—not from the Agent Cards page directly:

1. **[Publish](/graph-studio/publishing)** the agent graph.
2. **[Expose as External Agent](#expose-wizard)** via **Configure Agent** → **Create New Build**.
3. Return to Agent Cards to compare the new **test** row with existing builds.

### Permissions

| Action | Permission |
| ------ | ---------- |
| View builds | `assistants.flows:read` |
| Promote to live | `assistants.flows:update` |
| Sidebar entry | `workspace.sidebar.agent_registry` |

<a id="hosted-urls-and-lifecycle"></a>

## Hosted URLs and lifecycle
### Hosted A2A URLs

External callers reach registered agents through the **API gateway** AI-core lane. The frontend builds URLs with the same rules as `buildA2aUrl` in the product:

| Deployment status | URL pattern | Example shape |
| ----------------- | ----------- | ------------- |
| **Live** | `{gateway}/api/v1/ai/a2a/{flowId}` | Production routing; registry ID omitted |
| **Test** | `{gateway}/api/v1/ai/a2a/{flowId}/{registryId}` | Validation build tied to a specific registry row |

```text
# Live
https://app-dev.phinite.ai/api/v1/ai/a2a/{flowId}

# Test
https://app-dev.phinite.ai/api/v1/ai/a2a/{flowId}/{a2aregistryid}
```

Replace the host with your environment's gateway base (`NEXT_PUBLIC_BACKEND_SERVER_URL` → `/api/v1`, then append `/ai` for the AI-core lane). Graph Studio and Agent Registry copy the authoritative string for your tenant—always use the value shown in the UI rather than constructing URLs manually.

For local development with the dev API proxy, the same paths may appear under `http://localhost:3000/api/v1/ai/a2a/...`.

### Registry lifecycle

Each expose action creates an **A2A registry** row with deployment status **`test`** by default.

| Status | Meaning | Hosted URL |
| ------ | ------- | ---------- |
| **`test`** | Internal validation before broad discovery | Includes `{registryId}` in path |
| **`live`** | Production build for the agent graph | Short path with `{flowId}` only |

**One live build per agent graph per workspace.** Promoting a build to live demotes any previous live row for the same `flowid` back to **`test`**.

#### Promote to live

From **[Agent Cards and builds](#agent-cards-and-builds)**, select a test build and use **Push To Prod** (promote flow). The app calls:

```
PUT /api/v1/a2a-registry/{a2aregistryid}/promote-live
```

No request body is required. The response is the updated registry document with `status: "live"`.

### Visibility and authentication

Each Agent Card declares **visibility**:

| Visibility | UI label | Invoke behaviour (high level) |
| ---------- | -------- | ------------------------------ |
| **`public`** | Public | Callable by any client presenting a valid Phinite **API key** |
| **`organization`** | Organisation | Callable only when the API key belongs to the **same organisation** as the registry row |

At runtime, the gateway **`A2ARegistryAccess`** middleware validates visibility when agents are invoked (for example `POST /api/v1/ai/a2a/agents/{registryId}`). Organisation-scoped agents return an auth error if the caller's org does not match.

**Auth scheme in the product:** callers use your organisation's **API key** (JWT) in the `X-API-Key` header unless your deployment configures additional schemes.

### External clients (Claude Connector)

End users can call registry agents from **Claude** via the [Phinite Connector](/agent-registry/invoke-a2a-from-claude) without constructing A2A URLs manually.

| Layer | Behaviour |
| ----- | --------- |
| **Connector auth** | User signs in to Phinite (Google or email) when connecting the plugin in Claude |
| **Discovery** | `discover_agents` / `list_agents` query the same registry metadata as the workspace catalog |
| **Invocation** | `call_agent` maps to A2A `SendMessage` on `POST /api/v1/ai/a2a/agents/{registryId}` |
| **Multi-turn** | Pass `task_id` from a prior response to continue the same A2A task |
| **Tool credentials** | If the build requires integrations and no valid config exists, the runtime returns **`TASK_STATE_AUTH_REQUIRED`** with a link to **`/public/agent-config`** |

Full install steps, tool parameters, and credential lifecycle: **[Invoke A2A agents from Claude](/agent-registry/invoke-a2a-from-claude)**.

### Agent Card contract for integrators

Integrators and A2A-compatible clients should consume:

- **Agent name and description** from the Agent Card
- **Skills** — each skill lists supported **input modes** and **output modes** (MIME types)
- **Discoverability tags** — for search and Discovery matching
- **Hosted URL** — test vs live pattern above

See **[Terminology](/agent-registry/overview#terminology)** for supported MIME types.

Official protocol details: **[A2A protocol specification](https://a2a-protocol.org/latest/specification/)**.

### Registry management API

All routes require gateway authentication (session cookie or Bearer token / API key). Base path: **`/api/v1/a2a-registry`**.

| Method | Path | Purpose |
| ------ | ---- | ------- |
| `GET` | `/a2a-registry` | List registry rows (`workspaceid` required; optional `orgid`, `status`, `visibility`, `flowid`, filters) |
| `GET` | `/a2a-registry/{a2aregistryid}` | Get one row (`?flow=true` includes decrypted flow payload) |
| `POST` | `/a2a-registry?workspaceid=...` | Create registration (Expose wizard) |
| `PUT` | `/a2a-registry/{a2aregistryid}` | Update registration |
| `PUT` | `/a2a-registry/{a2aregistryid}/promote-live` | Promote to live |
| `DELETE` | `/a2a-registry/{a2aregistryid}` | Delete registration |

**Permissions (api-server):** `assistants.flows:read|create|update|delete` depending on operation.

#### Useful list query parameters

| Parameter | Values | Use |
| --------- | ------ | --- |
| `workspaceid` | string | **Required** — scopes to workspace |
| `orgid` | string | Organisation filter (must match caller's org) |
| `status` | `test`, `live` | Deployment filter |
| `visibility` | `public`, `organization` | Top-level visibility filter |
| `flowid` | string | All builds for one agent graph |
| `flow_list=true` | boolean | Returns distinct flows only (Agent Cards dropdown) |
| `pagination` | `true` / `false` | Paginated vs full list |

## Related pages

<CardGroup cols={2}>
<Card title="Invoke from Claude" href="/agent-registry/invoke-a2a-from-claude" icon="plug">
Phinite Connector install, tools, and credential setup.
</Card>
<Card title="Browse the catalog" href="/agent-registry/compose#catalog" icon="layout-grid">
Find and inspect registered agents.
</Card>
<Card title="Compose on canvas" href="/agent-registry/compose" icon="share-nodes">
Registry agent nodes in Browse and Discovery mode.
</Card>
<Card title="Overview" href="/agent-registry/overview" icon="circle-info">
End-to-end Agent Registry concepts and workflow.
</Card>
</CardGroup>
