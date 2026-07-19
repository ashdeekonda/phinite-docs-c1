---
title: Node types
description: Start, Master Agent, Child Agent, Tool, End, and registry agent nodes on the Agent Graph canvas.
---

**Nodes** are the building blocks of an Agent Graph. Connect them with edges to define how a **Conversational** or **Autonomous** run flows through your logic.

<Note>
  Legacy docs used **Block**; the product UI now uses **Node**.
</Note>

## Node types

| Node | Role | Deep dive |
| --- | --- | --- |
| **[Start](/graph-studio/nodes/start)** | Entry point when a run begins | Minimal drawer — one outbound handle |
| **Master Agent** | Orchestrator — prompt, tools, RAG, variables; registry agents | [Agent configuration](/graph-studio/agent-node) |
| **Child Agent** | Specialized sub-agent with its own prompt, tools, and variables | [Agent configuration](/graph-studio/agent-node) |
| **[Tool](/graph-studio/nodes/tool-node)** | Calls a published tool (API / integration) | Deterministic integration step |
| **[End](/graph-studio/nodes/end-node)** | Terminal node when the graph completes | Minimal drawer — inbound handle(s) |
| **Registry agent** | Calls an exposed A2A agent — **Browse** or **Discovery** | [Registry agent nodes](/agent-registry/registry-agent-nodes) |

<Frame caption="Agent Graph canvas with connected nodes">
  <img src="/images/v2/studio/04-nodes-canvas.png" alt="Nodes on the Graph Studio canvas" />
</Frame>

## Add nodes from the canvas toolbar

The **Node Library** is the add-node control on the canvas toolbar (not a separate sidebar). Use it to place nodes, then wire handles between them.

| Node | Use when |
| --- | --- |
| **Start** | Every graph needs one entry node |
| **Master Agent** | Primary reasoning step with full drawer tabs |
| **Child Agent** | Delegated sub-task with its own prompt and tools |
| **Tool** | Direct integration call without LLM orchestration |
| **End** | Run completes |

1. Open an Agent Graph in **Graph Studio**.
2. Click the add-node control on the canvas toolbar and choose a node type.
3. Click on the canvas to place it (or drag from the palette if your layout supports drag).
4. Drag from a source **handle** to a target **handle** to connect nodes ([Connections](/graph-studio/connections)).
5. Click **Master Agent** or **Child Agent** nodes to configure the [node drawer](/graph-studio/interface/inspector-panel).
6. Add an **[End](/graph-studio/nodes/end-node)** node where the run should finish.
7. Click **Save** before **Build**.

<Tip>
  Start with **Start** → **Master Agent** → **End** for a minimal graph, then add **Tool** and **Child Agent** nodes as needed.
</Tip>

## Registry agents (A2A)

Registry agents are attached from a **Master Agent** drawer (**Browse** / **Discovery**), not as a separate library tile.

1. Select the Master Agent node.
2. In the drawer, open the agent attachment flow (**Browse** or **Discovery**).
3. Pick a catalog agent or set discovery filters ([Registry agent nodes](/agent-registry/registry-agent-nodes)).

<Info>
  Only **one Discovery** node is allowed per Master Agent node.
</Info>

## Related

- [Graph Studio overview](/graph-studio/overview)
- [Agent configuration](/graph-studio/agent-node)
- [Interface layout](/graph-studio/interface)
