---
title: "Connecting Tools to Agents"
description: "Enable tools for agent nodes in Graph Studio and wire session variables to parameters."
---

Published tools from **Tools & Dev Studio** attach to **Master Agent**, **Child Agent**, and **Tool** nodes. Unpublished tools prompt you to **Publish** before **Build** pins versions.

## Link a tool to an agent node

1. Open the Agent Graph in [Graph Studio](/graph-studio/overview).
2. Select a **Master Agent** or **Child Agent** node (or a dedicated **Tool** node).
3. Open the node drawer → **Tools** tab.
4. Click **Add tool** (or **Connect tool**) and pick a **published** tool from the workspace or graph-scoped list.
5. If the tool needs an integration **connection**, select an existing connection or **Add a new connection** ([Integrations](/configure/integrations)).
6. Map **input variables** from the session to tool parameters where the UI exposes mapping fields.
7. Click **Save** on the Graph Studio toolbar before **Build**.

<Frame caption="Graph Studio — select an agent node and enable tools">
  <img src="/images/select-agent.png" alt="Agent node selected in Graph Studio canvas" />
</Frame>

<Frame caption="Tools tab — add and enable published tools">
  <img src="/images/enable-tools.png" alt="Agent node Tools tab with tool picker" />
</Frame>

<Frame caption="Map session variables to tool parameters">
  <img src="/images/map-variables.png" alt="Variable mapping between session and tool inputs" />
</Frame>

<Tip>
  Use `captured_variables` returned by tools to feed downstream nodes. Inspect captures in [Variable capture logs](/observability/logs/variables).
</Tip>

## Related

- [Agent node tools tab](/graph-studio/agent-node/tools)
- [Tool node](/graph-studio/nodes/tool-node)
- [Testing tools](/devstudio/testing-tools)
