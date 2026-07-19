---
title: Connections and logic
description: Handles, edges, and conditional branches on the Agent Graph canvas.
---

**Connections** define execution order: **handles** are attachment points; **edges** link nodes.

## Handles

Each node exposes **source** (outbound) and **target** (inbound) handles. Hover a node to reveal them. Only compatible pairs can be linked.

## Edges

1. Drag from a **source** handle on the upstream node.
2. Drop on a **target** handle on the downstream node.
3. **Save** the graph.

<Tip>
  Invalid connections are rejected in the UI.
</Tip>

## Conditional edges

Branch paths using **decision variables** on a **Master Agent**:

1. Open drawer → **Decision** tab → define decision variables.
2. Create multiple outbound edges from the node; label each edge per your design.
3. **Save** and **Test** every branch path to **End**.

<Warning>
  Dead branches cause incomplete runs — test all paths.
</Warning>

## Related

- [Node types](/graph-studio/nodes)
- [Variables — decision](/graph-studio/variables)
- [Agent configuration](/graph-studio/agent-node)
