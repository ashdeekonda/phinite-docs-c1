---
title: Master Agent node
description: Primary orchestrator node — prompt, tools, RAG, variables, and registry agents.
---

The **Master Agent** is the main reasoning node on the canvas. It supports the full [node drawer](/graph-studio/interface/inspector-panel): prompt, tools, RAG, variables, decision variables, and **Browse** / **Discovery** registry agents.

## Configuration

| Area | Drawer tab | Docs |
| --- | --- | --- |
| Name & prompt | **Details** | [Agent prompt](/graph-studio/agent-node/prompt) |
| Tools | **Tools** | [Tools integration](/graph-studio/agent-node/tools) |
| Knowledge | **RAG** | [RAG tab](/graph-studio/agent-node/rag) |
| Input / capture | **Variables** | [Variables](/graph-studio/agent-node/variables) |
| Branching | **Decision** | [Conditional edges](/graph-studio/connections/conditional-edges) |
| External agents | Browse / Discovery | [Registry agent nodes](/agent-registry/registry-agent-nodes) |

## Configure a Master Agent

1. Add a **Master Agent** node and connect it from **Start**.
2. Open the drawer and set **Details** (task prompt).
3. Attach **Tools** and **RAG** as needed.
4. Define **Input** and **Capture** variables.
5. Optionally add **Child Agent** or registry agent delegations.
6. **Save** the graph.

<Note>
  In the codebase this node type is implemented as the `task` node with configuration via Details, RAG, and Variables drawers.
</Note>

## Related

- [Agent node anatomy](/graph-studio/agent-node)
- [Child Agent node](/graph-studio/nodes/child-node)
