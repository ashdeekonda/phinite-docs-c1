---
title: RAG Management
description: Workspace RAG Data collections and attaching knowledge to agent nodes.
---

**RAG** grounds agent answers in your documents and structured data.

## Two layers

| Layer | Where | Purpose |
| --- | --- | --- |
| **RAG Data** | Workspace sidebar **RAG Data** | Create and index collections once |
| **Node attachment** | Graph Studio → agent **RAG** tab | Select sources per Master/Child Agent step |

<Frame caption="Workspace RAG Data — collections">
  <img src="/images/v2/rag/01-data-sources.png" alt="RAG Data workspace page" />
</Frame>

## Create collections

1. Open workspace **RAG Data**.
2. Create a **data source** and add documents or structured items.
3. Index collections before attaching to graphs.

Supported sources include PDF, CSV, text, datasets, and API-connected endpoints.

## Attach to an agent node

1. Open **Graph Studio** and select an agent node.
2. Open the **RAG** tab in the drawer.
3. Select **data source** and **items** for this step only.
4. **Save** the graph.

<Frame caption="Node drawer — RAG tab">
  <img src="/images/v2/rag/02-node-rag-drawer.png" alt="RAG tab on agent node" />
</Frame>

<Tip>
  Attach only collections relevant to each step — narrower retrieval improves answer quality.
</Tip>

## Builds and runtime

Attached RAG lists save with the graph version and pin on **Build**. See [Publishing](/graph-studio/publishing).

## Related

- [Agent configuration](/graph-studio/agent-node)
- [Graph Studio overview](/graph-studio/overview)
