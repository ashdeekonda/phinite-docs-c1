---
title: RAG overview
description: RAG Data in the workspace and attaching knowledge to agent nodes.
---

## What this is

**RAG** (retrieval-augmented generation) lets agents ground answers in your documents and structured data. Phinite splits this into two layers:

1. **RAG Data** — workspace collections you create and manage once.
2. **Node attachment** — each Master or Child Agent selects which collections/items to use at runtime.

## Where in the product

| Layer | Surface | Route |
| --- | --- | --- |
| Manage data | Workspace **RAG Data** | `/{org}/workspace/{workspaceId}/data-sources` |
| Attach to agents | Graph Studio → node drawer → **RAG** tab | Open graph in Studio, select node |

![RAG Data](/images/v2/rag/01-data-sources.png)

## Steps (high level)

1. Open **RAG Data** and create or open a data source / collection.
2. Upload or connect files and index content.
3. In **Graph Studio**, select an agent node → **RAG** tab.
4. Choose data sources and items relevant to that node.
5. **Save** the graph.

## Related

- [RAG Data sources](/rag/data-sources)
- [Attach RAG to nodes](/rag/attach-to-nodes)
- [Build an agent graph](/agents/build-graph)
