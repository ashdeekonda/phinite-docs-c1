---
title: End node
description: Terminal node where an Agent Graph run completes.
---

The **End** node marks successful completion of a graph path. Connect the last agent or tool step to **End**.

## Configuration

| Property | Notes |
| --- | --- |
| **Handles** | Inbound target handle(s) from upstream nodes |
| **Drawer** | Minimal configuration |

## Add an End node

1. Add an **End** node from the [Node Library](/graph-studio/interface/node-library).
2. Connect the final step(s) → **End**.
3. For graphs with branches, each terminal branch should reach an **End** (or explicit stop) as designed.
4. **Save** the graph.

## Related

- [Start node](/graph-studio/nodes/start)
- [Node types](/graph-studio/nodes)
- [Connections](/graph-studio/connections)
