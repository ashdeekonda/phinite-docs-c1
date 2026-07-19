---
title: Variables
description: Graph variables, node input/capture, session types, and decision variables.
---

Variables carry state through an Agent Graph at three layers: **graph schemas**, **per-node input/capture**, and **runtime session** values.

<Frame caption="Graph Studio variables panel">
  <img src="/images/v2/studio/03-variables.png" alt="Variables panel" />
</Frame>

## Variable layers

| Layer | Where | Purpose |
| --- | --- | --- |
| **Graph / flow variables** | [Variables panel](/graph-studio/interface) | Schemas and defaults for the whole graph |
| **Node input** | Drawer → **Variables** → Input | Map flow or session into an agent step |
| **Node capture** | Drawer → **Variables** → Capture | Fields the model extracts for downstream steps |
| **Session variables** | Runtime | User, system, tool-returned, and capture state |
| **Decision variables** | Drawer → **Decision** | Drive [conditional edges](/graph-studio/connections) |

## Graph variables

1. Open **Graph Studio** for your Agent Graph.
2. Open the **Variables** panel (when shown, or via `?tab=variables` where supported).
3. Define names, types, and defaults.
4. **Save** on the toolbar.

## Input variables

1. Select a **Master Agent** or **Child Agent** node → **Variables** tab.
2. Under **Input Variables**, map values from the flow or session.
3. **Save** the graph.

## Capture variables

1. Under **Capture Variables**, define fields the model should extract (name + description).
2. Downstream nodes and tools reference captured names.
3. **Save** the graph.

## Session variable types

| Type | How it is set |
| --- | --- |
| **Capture variables** | Agent extracts during the run |
| **Tool-returned capture** | Custom tools return `captured_variables`; predefined tools may store full output |
| **User variables** | Passed in the API payload before a run |
| **System variables** | Auto-set — e.g. `workflow_id`, `caller_number`, `conversation_history` |
| **Predefined tool output** | Entire tool output stored as session state |

<Frame caption="Predefined tool output as session state">
  <img src="/images/Screenshot2026-02-11at6.40.01PM.png" alt="Session variable example" />
</Frame>

<Note>
  Environment secrets (API keys, tokens) belong in [Env. variables](/configure/env-variables), not graph variable definitions.
</Note>

## Related

- [Agent configuration](/graph-studio/agent-node)
- [Interface — variables panel](/graph-studio/interface)
- [Variable capture logs](/observability/logs/variables)
