---
title: Conditional edges
description: Branch Agent Graph paths using decision variables from the node drawer.
---

**Conditional edges** route execution along labeled outbound paths when a **Master Agent** evaluates **decision variables**.

## Setup

1. Select a **Master Agent** node.
2. Open the drawer → **Decision** tab.
3. Define or select **decision variables** the model uses to choose a branch.
4. Create multiple outbound [edges](/graph-studio/connections/edges) from the node.
5. Label or configure each edge per your graph design (edge labels match decision outcomes in the Studio UI).
6. **Save** and test with **Test** using inputs that should trigger each branch.

<Warning>
  Test every branch path to **End** — dead branches cause incomplete runs.
</Warning>

## Related

- [Master Agent node](/graph-studio/nodes/master-node)
- [Agent node variables](/graph-studio/agent-node/variables)
- [Connections overview](/graph-studio/connections)
