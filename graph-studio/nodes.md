---
title: Node types
description: Start, Master Agent, Child Agent, Tool, End, and registry agent nodes.
---

**Nodes** are the building blocks of an Agent Graph.

<Note>
  Legacy docs used **Block**; the product UI now uses **Node**.
</Note>

## Node types

| Node | Role |
| --- | --- |
| **Start** | Entry point — one outbound handle; minimal drawer |
| **Master Agent** | Orchestrator — full drawer; **Browse** / **Discovery** registry agents |
| **Child Agent** | Delegated sub-task — own prompt, tools, RAG; **Child Variables** tab |
| **Tool** | Deterministic published tool call without LLM orchestration |
| **End** | Terminal node — run completes |
| **Registry agent** | Attached from Master Agent drawer — not a library tile |

<Frame caption="Agent Graph canvas with connected nodes">
  <img src="/images/v2/studio/04-nodes-canvas.png" alt="Nodes on the canvas" />
</Frame>

## Start node

Every graph needs exactly one **Start** node connected downstream. Minimal configuration — one outbound handle.

## Tool node

Executes a **published** tool without an LLM step. Select the tool and map inputs in the drawer. Tools must be published from [Tools & Dev Studio](/devstudio/overview) before **Build**.

## End node

Marks successful completion. Connect the final step(s) → **End**. Each branch should reach **End** (or an explicit stop).

## Master Agent vs Child Agent

| | **Master Agent** | **Child Agent** |
| --- | --- | --- |
| **Role** | Orchestrates the graph | Handles a delegated sub-task |
| **Registry agents** | **Browse** / **Discovery** | Not available |
| **Configuration** | [Agent configuration](/graph-studio/agent-node) | Same drawer tabs + **Child Variables** |

## Add nodes

1. Click the add-node control on the canvas toolbar.
2. Choose **Start**, **Master Agent**, **Child Agent**, **Tool**, or **End**.
3. Place on the canvas and connect [handles](/graph-studio/connections).
4. Configure Master/Child agents in the [drawer](/graph-studio/interface).
5. **Save** before **Build**.

<Tip>
  Start with **Start** → **Master Agent** → **End**, then add **Tool** and **Child Agent** as needed.
</Tip>

## Registry agents (A2A)

1. Select a **Master Agent** node.
2. In the drawer, attach **Browse** (fixed agent) or **Discovery** (filter-matched agents).
3. See [Registry agent nodes](/agent-registry/registry-agent-nodes). Only **one Discovery** per Master Agent.

## Related

- [Graph Studio overview](/graph-studio/overview)
- [Agent configuration](/graph-studio/agent-node)
