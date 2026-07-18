---
title: Variables panel
description: Flow variables, session variables, and graph-level schemas in Graph Studio.
---

The **Variables panel** manages graph-wide variable definitions — names, types, and defaults — separate from per-node **Input** and **Capture** settings in the [node drawer](/graph-studio/interface/inspector-panel).

<Frame caption="Graph Studio variables panel">
  <img src="/images/v2/studio/03-variables.png" alt="Variables panel in Graph Studio" />
</Frame>

## Variable layers

| Layer | Where | Purpose |
| --- | --- | --- |
| **Graph / flow variables** | Variables panel | Schemas and defaults for the whole Agent Graph |
| **Node input** | Drawer → **Variables** → Input | Read from flow or session into an agent step |
| **Node capture** | Drawer → **Variables** → Capture | Values the model extracts and persists for downstream steps |
| **Session variables** | Runtime | System and tool-returned values ([Session variable types](/graph-studio/types-of-session-variables)) |

## Graph variables

1. Open **Graph Studio** for your Agent Graph.
2. Open the **Variables** panel (when shown in your Studio layout, or via `?tab=variables` where supported).
3. Define variable names, types, and defaults required by your design.
4. Click **Save** on the toolbar.

## Node input and capture

1. Select a **Master Agent** or **Child Agent** node.
2. Open the **Variables** tab in the drawer.
3. Under **Input Variables**, map values available from the flow or session ([Input variables](/graph-studio/input-variables-in-agent-node)).
4. Under **Capture Variables**, define fields the model should extract ([Capture variables](/graph-studio/capture-variables-in-agent-node)).
5. **Save** the graph.

<Note>
  Environment secrets (API keys, tokens) belong in [Env. variables](/configure/env-variables), not in graph variable definitions.
</Note>

## Related

- [Agent node variables](/graph-studio/agent-node/variables)
- [Types of session variables](/graph-studio/types-of-session-variables)
- [Configuration overview](/configure/overview)
