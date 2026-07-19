---
title: Node types
description: Start, Master Agent, Child Agent, Tool, End, and registry agent nodes.
---

**Nodes** are the building blocks of an Agent Graph.

<Note>
  Legacy docs used **Block**; the product UI now uses **Node**.
</Note>

## Node types

| Node | Canvas type | Role |
| --- | --- | --- |
| **Start** | `start` | Entry point — one outbound handle; minimal drawer |
| **Master Agent** | `task` (labeled **Master Agent**) | Orchestrator — full drawer; registry **Browse** / **Discovery** |
| **Child Agent** | `child` | Delegated sub-task — **Purpose**, prompt, tools, RAG, Variables |
| **Tool** | `tool` | Deterministic published tool call without LLM orchestration |
| **End** | `end` | Terminal node — run completes |
| **Registry agent** | Attached from Master | Browse / Discovery — not a library tile |

Example graph (GitHub Repository Search): **Start** → Keyword Extraction (`task`) → Master Coordinator (`task`) → Child Markdown (`child`) → **End**.

<Frame caption="Agent Graph canvas — Master, Child, Start, End">
  <img src="/images/v2/studio/14-github-studio-shell.png" alt="Nodes on the Graph Studio canvas" />
</Frame>

## Start node

Every graph needs exactly one **Start** node connected downstream. Minimal configuration — one outbound handle.

## Tool node

Executes a **published** tool without an LLM step. Select the tool and map inputs in the drawer. Tools must be published from [Tools & Dev Studio](/devstudio/overview) before **Build**.

Many graphs attach tools on **Master / Child Agent** drawers instead of placing a standalone Tool node — both patterns are valid.

## End node

Marks successful completion. Connect the final step(s) → **End**. Each branch should reach **End** (or an explicit stop).

## Master Agent vs Child Agent

| | **Master Agent** | **Child Agent** |
| --- | --- | --- |
| **Role** | Orchestrates the graph | Handles a delegated sub-task |
| **Registry agents** | **Browse** / **Discovery** | Not available |
| **Configuration** | [Agent configuration](/graph-studio/agent-node) | Same tabs + **Purpose of this child agent** on Details |

## Add nodes

1. Use the floating node palette on the canvas.
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
