---
title: Node types
description: Start, Master Agent, Child Agent, Tool, End, and registry agent nodes on the Agent Graph canvas.
---

**Nodes** are the building blocks of an Agent Graph. Connect them with edges to define how a **Conversational** or **Autonomous** run flows through your logic.

<Note>
  Legacy docs used **Block**; the product UI now uses **Node**.
</Note>

## Node types

| Node | Role |
| --- | --- |
| **[Start](/graph-studio/nodes/start)** | Entry point when a run begins |
| **[Master Agent](/graph-studio/nodes/master-node)** | Orchestrator — prompt, tools, RAG, variables; can delegate to child or registry agents |
| **[Child Agent](/graph-studio/nodes/child-node)** | Specialized sub-agent with its own prompt, tools, and variables |
| **[Tool](/graph-studio/nodes/tool-node)** | Calls a published tool (API / integration) |
| **[End](/graph-studio/nodes/end-node)** | Terminal node when the graph completes |
| **Registry agent** | Calls an exposed A2A agent — **Browse** (fixed agent) or **Discovery** (filter-matched agents) |

<Frame caption="Agent Graph canvas with connected nodes">
  <img src="/images/v2/studio/04-nodes-canvas.png" alt="Nodes on the Graph Studio canvas" />
</Frame>

## Add nodes

1. Open an Agent Graph in **Graph Studio**.
2. Use the canvas toolbar or **Node Library** to add a node type ([Interface → Node Library](/graph-studio/interface/node-library)).
3. Drag from a source **handle** to a target **handle** to connect nodes ([Connections](/graph-studio/connections)).
4. Click a node to open the **node drawer** and configure [prompt, RAG, tools, and variables](/graph-studio/agent-node).
5. Add an **[End](/graph-studio/nodes/end-node)** node where the run should finish.
6. Click **Save** before **Build**.

## Registry agents (A2A)

To call another workspace agent over A2A, configure a registry agent under a **Master Agent**:

1. Select the Master Agent node.
2. In the drawer, open the agent attachment flow (**Browse** or **Discovery**).
3. Pick a catalog agent or set discovery filters ([Registry agent nodes](/agent-registry/registry-agent-nodes)).

<Info>
  Only **one Discovery** node is allowed per Master Agent node.
</Info>

## Related

- [Graph Studio overview](/graph-studio/overview)
- [Manual canvas method](/graph-studio/manual-method)
- [Agent node anatomy](/graph-studio/agent-node)
- [Variables](/graph-studio/interface/variables-panel)
- [Attach RAG](/graph-studio/rag-management/referencing)
