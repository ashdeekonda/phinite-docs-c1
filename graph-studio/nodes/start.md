---
title: Start node
description: Entry point for every Agent Graph run.
---

The **Start** node marks where execution begins when a graph runs. Every Agent Graph should have exactly one **Start** node connected downstream.

## Configuration

| Property | Notes |
| --- | --- |
| **Handles** | One outbound source handle to the first agent or tool step |
| **Drawer** | Minimal — no prompt/RAG/tools tabs |

## Add a Start node

1. Open [Graph Studio](/graph-studio/overview).
2. Add a **Start** node from the [Node Library](/graph-studio/interface/node-library).
3. Connect Start → **Master Agent** (or first step).
4. **Save** the graph.

## Related

- [Node types](/graph-studio/nodes)
- [Connections](/graph-studio/connections)
