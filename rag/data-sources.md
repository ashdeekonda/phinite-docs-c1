---
title: RAG Data sources
description: Create and manage RAG collections in the workspace.
---

## What this is

**RAG Data** is where you register knowledge collections before attaching them to agent nodes. Collections can hold documents, tables, and other indexed content used at inference time.

## Where in the product

| Surface | Path |
| --- | --- |
| Workspace sidebar | **RAG Data** |
| URL | `/{org}/workspace/{workspaceId}/data-sources` |
| Collection detail | `.../data-sources/{datasourceId}` |

![RAG Data list](/images/v2/rag/01-data-sources.png)

## Steps

1. Open **RAG Data** from the workspace sidebar.
2. Create a new data source or open an existing collection.
3. Add files or connect ingestion sources supported by your deployment.
4. Wait for indexing to complete (status shown in the collection UI).
5. In Graph Studio, attach indexed items to agent nodes ([Attach RAG](/rag/attach-to-nodes)).

## Notes

- RAG Data is workspace-scoped; any Agent Graph in the workspace can reference allowed collections.
- Permissions: `workspace.sidebar.datasources`.

## Related

- [RAG overview](/rag/overview)
- [Attach RAG to nodes](/rag/attach-to-nodes)
