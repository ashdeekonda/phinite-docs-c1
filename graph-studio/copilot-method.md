---
title: Phinite Aura (prompt-based)
description: Bootstrap an Agent Graph draft from a natural-language description, then refine on the canvas.
---

**Phinite Aura** (prompt-based creation) turns a plain-language goal into a draft canvas — nodes, edges, tool hints, and variable suggestions — that you accept, edit, or extend manually.

<Card title="After Aura generates a draft" type="note" href="/graph-studio/manual-method">
  Always review prompts, RAG, tools, and variables in the node drawer before Save and Build.
</Card>

## Create with Aura

1. Open **Graph Studio** or start **New Agent Graph** from Workspace Home.
2. Choose **Create with Aura** (or open the Aura panel on an existing graph).
3. Describe your objective: goal, inputs, knowledge sources, tools, and expected outputs.
4. Submit — Aura proposes **Start**, agent, **Tool**, and **End** nodes with connecting edges.
5. Review the draft on the canvas; open each node drawer and validate **Details**, **RAG**, **Tools**, and **Variables**.
6. Click **Save**.

<Frame caption="Graph Studio with Phinite Aura panel">
  <img src="/images/v2/studio/01-studio-aura-shell.png" alt="Graph Studio with Aura chat" />
</Frame>

## Prompt tips

| Include | Why |
| --- | --- |
| **Goal** | What the graph should achieve and for whom |
| **Inputs** | Variables and formats the run receives |
| **Knowledge** | RAG collections or domains to ground answers |
| **Tools** | APIs or integrations the graph should call |
| **Success criteria** | Expected outputs or acceptance checks |

<Tip>
  Name relevant [RAG Data](/graph-studio/rag-management/data-sources) collections and [Tools](/devstudio/overview) in your Aura prompt for better first drafts.
</Tip>

## Refine the draft

1. Replace generic prompts with domain-specific [agent prompts](/graph-studio/agent-node/prompt).
2. Attach real [RAG collections](/graph-studio/rag-management/referencing) per agent node.
3. Wire [input and capture variables](/graph-studio/agent-node/variables).
4. Remove or add nodes using the [manual canvas](/graph-studio/manual-method) workflow.
5. **Save**, then proceed to [Build](/builds/overview).

<Check>
  Before Save, confirm a clear path from **Start** to **End** and that branch labels match your [decision variables](/graph-studio/connections/conditional-edges).
</Check>

## Related

- [Manual canvas method](/graph-studio/manual-method)
- [Graph Studio overview](/graph-studio/overview)
