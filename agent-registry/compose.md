---
title: "Compose on canvas"
description: "Attach Agent Registry agents to master agent nodes in Browse or Discovery mode, and browse the workspace catalog."
---

<a id="registry-agent-nodes"></a>

## Registry agent nodes (Browse and Discovery)
Registry **agent nodes** connect a **master agent node** (task orchestrator) to agents published in the **[Agent Registry](/agent-registry/overview)**. Unlike a standard agent node configured only with prompts and tools, a registry agent node references an **A2A registration**—either a **specific** agent (**Browse**) or a **dynamic set** matched at runtime (**Discovery**).

![Browse and Discovery toggle on the agent node panel](/images/agent-registry/agent-node-browse-discovery-toggle.png)

<Info>
The browse panel title in the product reads **Agent Block**; documentation uses **Agent Node** for consistency with **[Graph Studio agent nodes](/graph-studio/agent-node)**.
</Info>

### When to use Browse vs Discovery

| Mode | Use when | Runtime behaviour |
| ---- | -------- | ----------------- |
| **Browse** | You know which registry agent to call | Master agent invokes the selected registration (fixed `a2aregistryid`, tools/env from that build) |
| **Discovery** | The right specialist agent depends on context | Master agent searches the registry using saved filters and attaches matching agents automatically |

Both modes require agents to be **exposed** in the registry with appropriate **visibility**, **skills**, and **tags**. See **[Expose wizard](/agent-registry/publish#expose-wizard)**.

### Open the registry panel

1. Open **Graph Studio** for your project.
2. Add or select an **agent node** on the canvas under a **master (task) agent node**.
3. When the node is unconfigured—or when you open registry tooling—the **Browse / Discovery** panel appears on the right.

The panel loads registry data via **`GET /a2a-registry?workspaceid=...&orgid=...`**.

### Browse mode

In **Browse** mode:

1. Search and filter agents (visibility, deployed status, MIME modes, tags)—same dimensions as **[Browse the catalog](#catalog)**.
2. Select an agent card from the list.
3. Review the **Agent Card preview** (hosted URL, skills, build status).
4. Click to **add** the agent to the canvas (or replace the current registry agent node).

After selection, configure **tools and environment variables** exported with that registry build in the **Configuration** sub-view. Browse nodes persist:

- `a2aregistryid`, `config_id`, `flowid`, `status`, `apikeyid`
- `agent_node_type: "browse"`

Validation requires a connected configuration (`config_id`) and satisfied tool/env requirements before save or publish.

### Discovery mode

In **Discovery** mode the master agent **does not** point at one fixed registration. Instead you define **Discovery filters**; at runtime the platform finds registry agents that match.

![Discovery filter panel with visibility, deployed, MIME, and tags](/images/agent-registry/discovery-filters.png)

#### Set Discovery filters

Configure filters parallel to the catalog sidebar:

| Filter | Purpose |
| ------ | ------- |
| **Visibility** | Public and/or Organisation |
| **Deployed** | Live and/or Test |
| **Input Modes** | MIME types callers may send |
| **Output Modes** | MIME types agents may return |
| **Tags** | Discoverability tags on Agent Cards |
| **Auth** | Auth scheme filters where applicable |

Click **Save Filters** to create a **Discovery Agent** node on the canvas with:

- `agent_node_type: "discovery"`
- `discovery_filters` — saved filter object
- Default display name: **Discovery Agent**

Copy shown in the UI:

> In Discovery Mode, the Master Agent will find and attach the agents automatically based on your filter criteria.

#### Configure Discovery API key

After saving filters, open the **Configuration** sub-tab to select the **API key** the master agent uses when calling discovered agents (`apikeyid` on the node).

![Discovery configuration with API key selection](/images/agent-registry/discovery-config.png)

#### One Discovery node per master agent

<Warning>
Only **one Discovery** registry agent node is allowed per **master (task) agent node**. If you try to add a second, the Studio shows **Discovery Already Connected** (or the Discovery tab is disabled with *Only one discovery allowed per master agent node*).
</Warning>

Discovery nodes **skip** the standard per-tool configuration validation used in Browse mode—the filter set defines what may be attached at runtime.

### Persisted node fields

When you save or publish the agent graph, registry agent nodes include:

| Field | Browse | Discovery |
| ----- | ------ | --------- |
| `agent_node_type` | `"browse"` | `"discovery"` |
| `a2aregistryid` | Selected registration | — |
| `config_id` | Build tool/env config | — |
| `discovery_filters` | — | Saved filter object |
| `apikeyid` | Optional | Required for runtime calls |
| `flowid`, `status` | From selected build | — |
| `integration_link` | A2A endpoint reference | — |

### Permissions

- Configure registry nodes: **`flow_gen.studio.save_flow`** and related Graph Studio permissions
- Load registry list: **`assistants.flows:read`**

<a id="catalog"></a>

## Browse the catalog
### Open Agent Registry

In the workspace sidebar, open **Agent Registry** when your organisation grants **`workspace.sidebar.agent_registry`**.

**Route:** `/{organisation}/workspace/{workspaceId}/agent-registry`

<Info>
The same registry data powers **Browse** mode on agent nodes in Graph Studio. The workspace page is the full catalog experience with search, filters, and detail views.
</Info>

![Agent Registry search and filter sidebar](/images/agent-registry/registry-search.png)

### Page layout

| Area | Description |
| ---- | ----------- |
| **Hero** | Heading *Find the Perfect AI Agent* with subtitle and agent count |
| **Search** | *Search for agents...* — filters by name, summary, tags, and related metadata |
| **Filter sidebar** | Visibility, deployed status, input/output MIME modes, and tags |
| **View toggle** | Grid or list layout |
| **Detail** | Selecting an agent opens a detail view (skills, status, visibility, copyable endpoint) |

![Filter sidebar with visibility, deployed status, and MIME modes](/images/agent-registry/registry-filters.png)

#### Filter dimensions

| Filter | Options | Purpose |
| ------ | ------- | ------- |
| **Visibility** | Public, Organisation | Match Agent Card visibility |
| **Deployed** | Live, Test | Match registry build status |
| **Input Mode** | MIME types (e.g. `text/plain`, `application/json`) | Skill input compatibility |
| **Output Mode** | MIME types | Skill output compatibility |
| **Tags** | Discoverability tags from Agent Cards | Narrow by topic or capability |

Filters apply **client-side** on the loaded registry list in addition to API query parameters described below.

### Organisation vs public listings

The UI distinguishes **Organisation** and **Public** catalog views internally (filter logic and API params). There is no separate **Sample** demo tab in the current product.

| View | API behaviour | What you see |
| ---- | ------------- | ------------ |
| **Organisation** | `GET /a2a-registry?workspaceid=...&orgid=...&pagination=false` | Test and live builds registered under your organisation |
| **Public-oriented** | Same request with **`status=live`** | Live builds only—intended for catalogue-style discovery |

<Warning>
Public-oriented filtering currently emphasises **`status=live`** at the API. **Visibility** (`public` vs `organization`) is stored on each registration and enforced at **invoke time** by the gateway; the catalog may show mixed visibility until you apply the **Public** visibility filter in the sidebar.
</Warning>

### Agent cards in the list

Each card typically shows:

- Agent name and description (from **Agent Card**)
- Deployment badge (**Test** or **Live**)
- Visibility (**Public** or **Organisation**)
- Skills summary and discoverability tags
- Hosted **A2A URL** (live builds omit the registry ID in the path—see **[Hosted URLs and lifecycle](/agent-registry/publish#hosted-urls-and-lifecycle)**)

![Agent detail with skills, endpoint, and build information](/images/agent-registry/registry-detail.png)

Selecting a card opens a detail panel or modal where you can copy the endpoint and review build metadata.

### API reference (listing)

The catalog loads registry rows via the gateway:

```
GET /api/v1/a2a-registry?workspaceid={id}&orgid={id}&pagination=false
GET /api/v1/a2a-registry?workspaceid={id}&orgid={id}&status=live&pagination=false
```

Optional query params supported by the API include `flowid`, `visibility`, `tag`, `input_mode`, `output_mode`, and paginated `page`/`limit`. The workspace page currently loads the full list with `pagination=false` for client-side search and filters.

### Permissions

- **View registry:** `assistants.flows:read` (via gateway auth)
- **Sidebar entry:** `workspace.sidebar.agent_registry`

## Related pages

<CardGroup cols={2}>
<Card title="Expose an agent" href="/agent-registry/publish#expose-wizard" icon="rocket">
Create a new registry entry from Graph Studio.
</Card>
<Card title="Hosted URLs and lifecycle" href="/agent-registry/publish#hosted-urls-and-lifecycle" icon="plug">
Hosted URLs and visibility at invoke time.
</Card>
<Card title="Agent node anatomy" href="/graph-studio/agent-node" icon="cube">
Prompts, RAG, tools, and variables on standard agent nodes.
</Card>
<Card title="Overview" href="/agent-registry/overview" icon="circle-info">
End-to-end Agent Registry concepts and workflow.
</Card>
</CardGroup>
