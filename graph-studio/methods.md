---
title: Graph creation methods
description: Build Agent Graphs with Phinite Aura or the manual canvas.
---

Choose how you bootstrap and refine an Agent Graph. Both methods use the same canvas, drawer, and **Save** → **Build** workflow.

## Phinite Aura (prompt-based)

**Aura** turns a plain-language goal into a draft canvas — nodes, edges, tool hints, and variable suggestions.

1. Open **Graph Studio** or start **New Agent Graph**.
2. Choose **Create with Aura** (or open the Aura panel).
3. Describe goal, inputs, knowledge sources, tools, and expected outputs.
4. Review the draft; validate each node drawer (**Details**, **Tools**, **RAG**, **Variables**).
5. Refine on the canvas, then **Save**.

<Frame caption="Graph Studio with Phinite Aura panel">
  <img src="/images/v2/studio/01-studio-aura-shell.png" alt="Graph Studio with Aura chat" />
</Frame>

| Include in your prompt | Why |
| --- | --- |
| **Goal** | What the graph should achieve |
| **Inputs** | Variables and formats the run receives |
| **Knowledge** | RAG collections to ground answers |
| **Tools** | APIs or integrations to call |
| **Success criteria** | Expected outputs |

<Tip>
  Name relevant RAG collections and [Tools](/devstudio/overview) in your Aura prompt for better first drafts.
</Tip>

Before **Save**, confirm a clear path from **Start** to **End** and that branch labels match [decision variables](/graph-studio/connections).

## Manual canvas

Use the manual canvas for full control over placement, edge order, and drawer configuration.

1. **New Agent Graph** → choose **Conversational** or **Autonomous** → **Create**.
2. **Add nodes** from the toolbar ([Node types](/graph-studio/nodes)).
3. **Connect edges** ([Connections](/graph-studio/connections)).
4. **Configure the drawer** ([Agent configuration](/graph-studio/agent-node)).
5. **Test** from the toolbar, then **Save**.

<Frame caption="Configure a node in the drawer">
  <img src="/images/v2/rag/02-node-rag-drawer.png" alt="Node drawer tabs" />
</Frame>

### Iterate

1. Run sample inputs from **Test**.
2. Refine prompts, RAG, and [variables](/graph-studio/variables).
3. Adjust [conditional edges](/graph-studio/connections) for branching graphs.
4. **Save** after each meaningful change.

## Related

- [Graph Studio overview](/graph-studio/overview)
- [Publishing](/graph-studio/publishing)
