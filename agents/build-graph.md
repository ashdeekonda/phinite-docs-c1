---
title: Build an agent graph
description: Design nodes, tools, RAG, and variables in Graph Studio.
---

Open an Agent Graph from Workspace Home (opens Graph Studio).

## Studio layout

- Left nav: **Agent Graphs**, **Evaluations**, **Governance**, then **Graph assets** (Versions, Builds, Cards, Triggers, Integrations, Tools).
- Canvas: [Node types](/studio/nodes) — Start, Master/Child Agent, Tool, End, registry agents.
- Toolbar: **Save**, **Build**, **Deploy**, **Test**.
- Optional: **Phinite Aura** chat for assisted edits.

![Graph Studio](/images/v2/studio/01-studio-aura-shell.png)

## Steps

1. Open or create an Agent Graph ([Agents overview](/agents/overview)).
2. Add and connect [nodes](/studio/nodes) on the canvas.
3. Configure each node in the drawer:
   - **Prompt** — mission and instructions
   - **Tools** — attach published tools ([Tools](/tools/overview))
   - **RAG** — attach collections ([Attach RAG](/rag/attach-to-nodes))
   - **Variables** — input and capture ([Variables](/studio/variables))
   - **Model** — provider and key ([Model Keys](/workspace/models))
4. Optionally compose external agents via [Browse / Discovery](/a2a/discovery).
5. Click **Save** before **Build**.

## Configuration map

See [Configuration overview](/configure/overview) for env variables, integrations, and build export.

## Related

- [Node types](/studio/nodes)
- [RAG overview](/rag/overview)
- [Variables](/studio/variables)
- [Tools](/tools/overview)
- [Builds](/agents/builds)
