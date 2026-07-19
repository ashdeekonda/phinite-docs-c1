---
title: Graph Studio overview
description: Design Agent Graphs on the canvas — nodes, tools, RAG, variables — then Save before Build.
---

**Graph Studio** is where you design an **Agent Graph**: connect [nodes](/graph-studio/nodes), configure each step in the **node drawer**, and use the toolbar to **Save**, **Build**, **Deploy**, and **Test**.

<CardGroup cols={2}>
  <Card title="Manual canvas" icon="pencil" href="/graph-studio/manual-method">
    Drag nodes, connect edges, and configure the drawer tab by tab.
  </Card>
  <Card title="Phinite Aura" icon="sparkles" href="/graph-studio/copilot-method">
    Describe the graph in natural language; refine the draft on the canvas.
  </Card>
  <Card title="Node types" icon="diagram-project" href="/graph-studio/nodes">
    Start, Master Agent, Child Agent, Tool, End, and registry agents.
  </Card>
  <Card title="RAG Management" icon="book" type="note" href="/graph-studio/rag-management">
    Ground agents with workspace RAG Data collections.
  </Card>
</CardGroup>

## Studio layout

| Area | What it does |
| --- | --- |
| **Left sidebar** | **Agent Graphs**, **Evaluations**, **Governance**; **Graph assets** — Versions, Builds, Cards, Triggers, Integrations, Tools |
| **Canvas** | React Flow graph — add and connect [nodes](/graph-studio/nodes) |
| **Node drawer** | Opens when you select a node — **Details**, **RAG**, **Variables**, **Tools**, **Decision** (see [Inspector](/graph-studio/interface/inspector-panel)) |
| **Toolbar** | **Save** → **Build** → **Deploy** → **Test** (Build/Deploy stay disabled until prerequisites are met) |
| **Phinite Aura** | Optional chat panel for assisted graph edits |

<Frame caption="Graph Studio — canvas, Aura, and Save / Build / Deploy / Test toolbar">
  <img src="/images/v2/studio/01-studio-aura-shell.png" alt="Graph Studio shell with toolbar and canvas" />
</Frame>

## Open Graph Studio

1. From **Workspace Home**, open an existing **Agent Graph** or click **New Agent Graph**.
2. In the **New Agent Graph** dialog, enter name and description and choose **Conversational** or **Autonomous** ([Agents overview](/agents/overview)).
3. Click **Create** — Studio opens on the canvas for that graph.

<Note>
  Workspace filters may still show an **Email** chip. New graphs only offer **Conversational** and **Autonomous**.
</Note>

## Design workflow

1. Add and connect [nodes](/graph-studio/nodes) on the canvas ([Manual method](/graph-studio/manual-method) or [Aura](/graph-studio/copilot-method)).
2. Select each **Master Agent** or **Child Agent** node and configure the drawer:
   - **[Prompt](/graph-studio/agent-node/prompt)** — mission and instructions
   - **[Tools](/graph-studio/agent-node/tools)** — attach published tools
   - **[RAG](/graph-studio/rag-management/referencing)** — attach collections from [RAG Data](/graph-studio/rag-management/data-sources)
   - **[Variables](/graph-studio/agent-node/variables)** — input and capture
3. Define graph-level variables in the [Variables panel](/graph-studio/interface/variables-panel) when your layout includes it.
4. Click **Save** on the toolbar — required before **Build**.
5. Continue to [Builds](/builds/overview) and [Deploy](/agents/deploy) when the graph is ready.

<Tip>
  **Save** persists the draft graph. **Build** freezes graph + tool versions into an immutable **Agent Build** used for environment assignment and deploy.
</Tip>

## Graph assets (sidebar)

| Asset | Purpose |
| --- | --- |
| **Graph Versions** | Saved snapshots of the graph |
| **Agent Builds** | Pinned builds created from the **Build** dialog |
| **Agent Cards** | A2A exposure for this graph |
| **Triggers** | Graph-scoped triggers (hub links to [Integrations](/configure/integrations)) |
| **Integrations** | Graph-scoped channels and tools |
| **Tools** | Graph-scoped tool list |

<Frame caption="Studio Tools panel — graph-scoped tools">
  <img src="/images/v2/studio/02-tools-sidebar.png" alt="Graph Studio Tools sidebar panel" />
</Frame>

## Related

- [Interface layout](/graph-studio/interface)
- [Agent node anatomy](/graph-studio/agent-node)
- [Connections & logic](/graph-studio/connections)
- [Publishing & versions](/graph-studio/publishing)
- [Configuration overview](/configure/overview)
- [Agent Registry (A2A)](/agent-registry/overview)
