---
title: Manual canvas method
description: Design Agent Graphs by placing nodes on the canvas and configuring the node drawer.
---

Use the **manual canvas** when you want full control over node placement, edge order, and drawer configuration.

<Card title="Recommended for learning" type="tip" href="/graph-studio/overview">
  Manual editing is the best way to understand how nodes, variables, and conditional edges interact.
</Card>

## Create a graph manually

1. From **Workspace Home**, click **New Agent Graph**.
2. Enter name and description; choose **Conversational** or **Autonomous**.
3. Click **Create** — Studio opens an empty or starter canvas.

<Frame caption="New Agent Graph dialog — name, type, and Create">
  <img src="/images/v2/agents/01-new-agent-graph-modal.png" alt="New Agent Graph modal" />
</Frame>

## Build on the canvas

1. **Add nodes** — From the canvas toolbar, add **Start**, **Master Agent**, **Child Agent**, **Tool**, and **End** nodes ([Node types](/graph-studio/nodes)).
2. **Connect edges** — Drag from a source handle to a target handle ([Handles & edges](/graph-studio/connections/handles)).
3. **Configure the drawer** — Select a node; set **Details** (prompt), **Tools**, **RAG**, and **Variables** in the [Inspector](/graph-studio/interface/inspector-panel).
4. **Graph variables** — Open the [Variables panel](/graph-studio/interface/variables-panel) when available for flow-wide schemas.
5. **Test** — Use toolbar **Test** (chat, voice, email, or autonomous test drawer depending on graph type).
6. **Save** — Click **Save** before creating a build.

<Frame caption="Configure a node in the drawer — Details, RAG, Variables, Tools">
  <img src="/images/v2/rag/02-node-rag-drawer.png" alt="Node drawer with RAG tab" />
</Frame>

## Iterate

1. Run sample inputs from **Test**.
2. Refine prompts, RAG attachments, and [capture variables](/graph-studio/capture-variables-in-agent-node).
3. Adjust [conditional edges](/graph-studio/connections/conditional-edges) if the graph branches on decision variables.
4. **Save** again after each meaningful change.

<Tip>
  Use variables to pass context between agents and tools instead of repeating extraction in every prompt.
</Tip>

## Related

- [Phinite Aura method](/graph-studio/copilot-method)
- [Graph Studio overview](/graph-studio/overview)
- [Publishing](/graph-studio/publishing)
