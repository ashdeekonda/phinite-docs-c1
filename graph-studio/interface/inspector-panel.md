---
title: Inspector (node drawer)
description: Configure the selected node — Details, RAG, Variables, Tools, and Decision tabs.
---

When you select a node on the canvas, the **node drawer** (Inspector) opens on the side. It is implemented as `NodeDrawer` in the Studio codebase.

<Frame caption="Node drawer — RAG tab on a Master Agent node">
  <img src="/images/v2/rag/02-node-rag-drawer.png" alt="Node drawer RAG tab" />
</Frame>

## Drawer tabs

| Tab | Configures |
| --- | --- |
| **Details** | Name, description, main **task prompt** ([Agent prompt](/graph-studio/agent-node/prompt)) |
| **Tools** | Published tools attached to this agent ([Tools tab](/graph-studio/agent-node/tools)) |
| **RAG** | Data sources and items from [RAG Data](/graph-studio/rag-management/data-sources) ([Attach RAG](/graph-studio/rag-management/referencing)) |
| **Variables** | Input and capture variables ([Variables tab](/graph-studio/agent-node/variables)) |
| **Decision** | Variables used for [conditional edges](/graph-studio/connections/conditional-edges) |
| **Child Variables** | On **Child Agent** nodes — variables scoped to the child |

## Configure a node

1. Click a **Master Agent** or **Child Agent** node on the canvas.
2. Work through **Details** → **Tools** → **RAG** → **Variables** (order flexible).
3. For branching graphs, set **Decision** variables before wiring conditional edges.
4. Close the drawer or select another node — changes stay in the draft until **Save**.

<Tip>
  Use **Refine with AI** in **Details** (when available) to tighten prompts before Save.
</Tip>

## Modals from the drawer

Some actions open nested dialogs:

| Action | Dialog |
| --- | --- |
| Connect a tool | **Connect Tool** — pick a published tool |
| Add MCP | **Add MCP Connection** |
| API key / model | **Connect API Key** / **Change API** |
| Create variable | **Create Variable** |
| Session variables | **Session Variables** |

Document each screen when writing step-by-step guides; capture one framed screenshot per dialog.

## Related

- [Agent node anatomy](/graph-studio/agent-node)
- [Interface layout](/graph-studio/interface)
