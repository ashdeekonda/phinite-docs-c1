---
title: Connection handles
description: Source and target handles on Graph Studio nodes.
---

Each node exposes **handles** — small ports used to create [edges](/graph-studio/connections/edges).

## Handle types

| Handle | Direction | Meaning |
| --- | --- | --- |
| **Source** | Outbound | Execution continues to the connected downstream node |
| **Target** | Inbound | Accepts a connection from an upstream node |

## Connect handles

1. Select the upstream node and locate its **source** handle (usually on the right or bottom).
2. Drag to the **target** handle on the downstream node.
3. Release to create an edge.

<Note>
  **Start** has outbound handles only; **End** has inbound handles only.
</Note>

## Related

- [Connections overview](/graph-studio/connections)
- [Edges](/graph-studio/connections/edges)
