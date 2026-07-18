---
title: Edges
description: Links between nodes that define execution order on the canvas.
---

An **edge** connects a source handle on one node to a target handle on another. Edges define the default execution path through the Agent Graph.

## Create an edge

1. Drag from a **source** handle ([Handles](/graph-studio/connections/handles)).
2. Drop on a **target** handle of the next node.
3. Repeat until every path flows **Start** → … → **End**.
4. **Save** the graph.

## Multiple outbound edges

When a **Master Agent** has multiple outbound edges, execution may branch based on [decision variables](/graph-studio/connections/conditional-edges) or graph semantics defined in your design.

## Related

- [Connections overview](/graph-studio/connections)
- [Conditional edges](/graph-studio/connections/conditional-edges)
