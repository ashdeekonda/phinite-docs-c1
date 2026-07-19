---
title: Interface layout
description: Canvas, toolbar, node drawer, and graph assets in Graph Studio.
---

Graph Studio splits design work across the **canvas**, **toolbar**, **node drawer**, and **graph assets** sidebar. **Phinite Aura** sits in the left nav for chat-driven edits.

## Canvas

- React Flow graph — pan, zoom, and arrange [nodes](/graph-studio/nodes).
- Add nodes from the **floating node palette** on the canvas.
- Drag **handles** to create [connections](/graph-studio/connections).
- Bottom controls: **With Prompt** / view mode, lock, fit, organize, zoom, undo/redo.

<Frame caption="Graph Studio — GitHub Repository Search graph">
  <img src="/images/v2/studio/14-github-studio-shell.png" alt="GitHub graph canvas with Master and Child agents" />
</Frame>

## Toolbar

| Control | Action |
| --- | --- |
| **Save** | Persist the current graph draft (required before Build) |
| **Build** | Opens **Build Agent** — pins graph + tool versions |
| **Deploy** | Opens **Deploy Agent Build** — enabled when at least one build exists |
| **Test** | Chat, voice, or autonomous test drawer |
| **More actions** | Edit, Rename, Duplicate, Delete / Archive |

**Deploy** opens a modal with three tabs: **Deploy as A2A**, **Deploy to Channel**, and **Deploy as Chat API**. See [Expose as A2A](/agent-registry/expose-your-flow).

## Node drawer

Double-click a node (or select and open the panel) to configure it. Tabs on Master / Child agents:

| Tab | Configures |
| --- | --- |
| **Details** | **Orchestration Model**, **Agent Task Prompt** (Markdown / Formatted), **Refine Prompt**. Child agents also have **Purpose of this child agent**. |
| **RAG** | Attach workspace files / data sources (**Attach Files**) |
| **Tools** | Attached tools — **Add a new tool** |
| **Variables** | **Input Variables** and **Capture Variables** |

<Frame caption="Node drawer — Details tab (Master Agent)">
  <img src="/images/v2/studio/06-node-drawer-details.png" alt="Master Agent Details tab with orchestration model and task prompt" />
</Frame>

<Frame caption="Node drawer — Variables tab (Capture)">
  <img src="/images/v2/studio/07-node-drawer-variables.png" alt="Capture Variables on Master Agent" />
</Frame>

<Frame caption="Node drawer — RAG tab">
  <img src="/images/v2/studio/11-node-drawer-rag.png" alt="RAG tab with Attach Files" />
</Frame>

### Add a new tool

**Tools** → **Add a new tool** opens a side panel with three sources:

| Tab | Contents |
| --- | --- |
| **Tools** | Workspace tools (search **Search Workspace Tools**) |
| **Integrations** | Connected Integrations Hub apps |
| **MCP Servers** | Installed MCP servers (**+ Add** when empty) |

<Frame caption="Add a new tool — workspace Tools tab">
  <img src="/images/v2/studio/15-add-tool-github.png" alt="Add tool panel listing workspace tools" />
</Frame>

## Left sidebar — Graph assets

Under **GRAPH ASSETS** (graph-scoped):

| Asset | What you see |
| --- | --- |
| **Graph Versions** | Saved design snapshots |
| **Agent Builds** | Immutable builds + **DEV / UAT / PROD** environment assignments |
| **Agent Cards** | A2A registry versions — **Active deployments** (LIVE / Latest) |
| **Triggers** | API and other triggers bound to this graph |
| **Integrations** | Integrations used by the graph |
| **Tools** | Tools referenced on the canvas |

Also in the sidebar: **Phinite Aura**, workspace links (**Agent Graphs**, **Evaluations**, **Governance**).

<Frame caption="Agent Builds — environment assignments and build list">
  <img src="/images/v2/studio/19-github-agent-builds.png" alt="Agent Builds sidebar with DEV UAT PROD" />
</Frame>

<Frame caption="Triggers — graph-scoped API triggers">
  <img src="/images/v2/studio/18-github-triggers.png" alt="Triggers asset panel" />
</Frame>

## Related

- [Graph Studio overview](/graph-studio/overview)
- [Agent configuration](/graph-studio/agent-node)
- [Node types](/graph-studio/nodes)
