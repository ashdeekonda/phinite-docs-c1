---
title: Interface layout
description: Canvas, toolbar, node drawer, and variables panel in Graph Studio.
---

Graph Studio splits design work across the **canvas**, **toolbar**, **node drawer**, and **variables panel**.

## Canvas

- React Flow graph — pan, zoom, and arrange [nodes](/graph-studio/nodes).
- Add nodes from the **toolbar add-node control** (Node Library).
- Drag **handles** to create [connections](/graph-studio/connections).

<Frame caption="Graph Studio — canvas and toolbar">
  <img src="/images/v2/studio/01-studio-aura-shell.png" alt="Graph Studio shell" />
</Frame>

## Toolbar

| Control | Action |
| --- | --- |
| **Save** | Persist the current graph draft (required before Build) |
| **Build** | Open build dialog — pins graph + tool versions |
| **Deploy** | Open deploy dialog — requires at least one build |
| **Test** | Chat, voice, or autonomous test drawer |

## Node drawer (Inspector)

When you select a node, the drawer opens with tabs:

| Tab | Configures |
| --- | --- |
| **Details** | Task prompt ([Agent configuration](/graph-studio/agent-node)) |
| **Tools** | Published tools on this step |
| **RAG** | Data sources from [RAG Management](/graph-studio/rag-management) |
| **Variables** | Input and capture ([Variables](/graph-studio/variables)) |
| **Decision** | Branch variables for conditional edges |

<Frame caption="Node drawer — RAG tab">
  <img src="/images/v2/rag/02-node-rag-drawer.png" alt="Node drawer" />
</Frame>

### Modals from the drawer

| Action | Dialog |
| --- | --- |
| Connect a tool | **Connect Tool** |
| Add MCP | **Add MCP Connection** |
| API key / model | **Connect API Key** / **Change API** |
| Create variable | **Create Variable** |

## Variables panel

Graph-wide variable schemas — separate from per-node Input/Capture. See [Variables](/graph-studio/variables).

## Left sidebar

**Graph assets:** Graph Versions, Agent Builds, Agent Cards, Triggers, Integrations, Tools. See [Graph Studio overview](/graph-studio/overview).

## Related

- [Graph Studio overview](/graph-studio/overview)
- [Node types](/graph-studio/nodes)
