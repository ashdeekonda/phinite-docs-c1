---
title: Agent node variables
description: Input and capture variables on Master and Child Agent nodes.
---

The drawer **Variables** tab defines what flows **into** an agent step (**Input**) and what the step **extracts** for downstream use (**Capture**).

<Frame caption="Variables panel and node drawer Variables tab">
  <img src="/images/v2/studio/03-variables.png" alt="Variables in Graph Studio" />
</Frame>

## Input variables

1. Select an agent node → **Variables** tab.
2. Under **Input Variables**, map values from flow or [session variables](/graph-studio/types-of-session-variables).
3. **Save** the graph.

See [Input variables in agent nodes](/graph-studio/input-variables-in-agent-node).

## Capture variables

1. Under **Capture Variables**, define fields the model should extract (name + description).
2. Downstream nodes and tools reference captured names.
3. **Save** the graph.

See [Capture variables in agent nodes](/graph-studio/capture-variables-in-agent-node).

## Decision variables

Use captured values in the **Decision** tab to drive [conditional edges](/graph-studio/connections/conditional-edges).

## Related

- [Variables panel](/graph-studio/interface/variables-panel)
- [Agent node anatomy](/graph-studio/agent-node)
