---
title: Node types
description: Start, Master Agent, Child Agent, Tool, End, and registry agent nodes on the canvas.
---

## What this is

**Nodes** are the building blocks of an Agent Graph on the Graph Studio canvas. Connect them with edges to define how conversation or autonomous work flows.

Legacy docs used **Block**; the product now uses **Node**.

## Node types

| Node | Role |
| --- | --- |
| **Start** | Entry point when a run begins |
| **Master Agent** | Orchestrator: prompt, tools, RAG, variables; can delegate to child or registry agents |
| **Child Agent** | Specialized sub-agent with its own prompt, tools, and variables |
| **Tool** | Calls a published tool (API / integration) |
| **End** | Terminal node when the graph completes |
| **Registry agent** | Calls an exposed A2A agent (**Browse** = fixed agent; **Discovery** = filter-matched agents) |

## Where in the product

| Surface | How |
| --- | --- |
| Graph Studio canvas | Add nodes from the canvas toolbar / drag-connect |
| Node drawer | Configure prompt, Tools, RAG, Variables per node |

![Nodes on canvas](/images/v2/studio/04-nodes-canvas.png)

## Steps

1. Open an Agent Graph in **Graph Studio**.
2. Add a **Start** node if the graph is empty.
3. Add a **Master Agent** (or **Child Agent**) for reasoning steps.
4. Attach **Tool** nodes where an integration call is needed.
5. Connect nodes with edges (handles show valid connection points).
6. Add an **End** node where the run should finish.
7. **Save** before **Build**.

## Registry agents

To call another workspace agent over A2A, add an agent node under a Master Agent and use **Browse** or **Discovery**. See [A2A discovery](/a2a/discovery).

## Related

- [Build an agent graph](/agents/build-graph)
- [Variables](/studio/variables)
- [Attach RAG](/rag/attach-to-nodes)
- [A2A discovery](/a2a/discovery)
