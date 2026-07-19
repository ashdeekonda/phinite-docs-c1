---
title: Connections and logic
description: Connect nodes with handles and edges; branch with decision variables.
---

**Connections** define execution order on the Agent Graph canvas: **handles** are attachment points; **edges** are the links between nodes.

<CardGroup cols={2}>
  <Card title="Handles" icon="circle-nodes" href="/graph-studio/connections/handles">
    Source and target connection points on each node.
  </Card>
  <Card title="Edges" icon="arrow-right" href="/graph-studio/connections/edges">
    Execution order and data flow between steps.
  </Card>
  <Card title="Conditional edges" icon="code-branch" href="/graph-studio/connections/conditional-edges">
    Branch paths using decision variables from the drawer.
  </Card>
</CardGroup>

## Connect two nodes

1. Hover a node to reveal **handles**.
2. Drag from a **source** handle on the upstream node.
3. Drop on a **target** handle on the downstream node.
4. **Save** the graph.

<Tip>
  Invalid connections are rejected — only compatible handle pairs can be linked.
</Tip>

## Related

- [Canvas](/graph-studio/interface/canvas)
- [Agent configuration](/graph-studio/agent-node)
