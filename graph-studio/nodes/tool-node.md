---
title: Tool node
description: Call a published tool (API or integration) directly on the canvas.
---

A **Tool** node executes a published tool without an LLM orchestration step. Use it when the graph should call an integration deterministically.

## Configure

1. Add a **Tool** node from the [Node Library](/graph-studio/interface/node-library).
2. Connect upstream from an agent or **Start** as your design requires.
3. Select the tool and map inputs (in the node drawer or tool configuration UI).
4. Connect downstream to the next agent, tool, or **End**.
5. **Save** the graph.

<Tip>
  Tools must be **published** from [Tools & Dev Studio](/devstudio/overview) before they appear in the picker. Unpublished tools show **Publish** in the **Build** dialog.
</Tip>

## Related

- [Agent node tools tab](/graph-studio/agent-node/tools)
- [Node types](/graph-studio/nodes)
