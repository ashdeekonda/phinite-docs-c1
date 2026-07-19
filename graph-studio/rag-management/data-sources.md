---
title: RAG Data sources
description: Create and manage RAG collections in the workspace before attaching them to agent nodes.
---

**RAG Data** is where you register knowledge collections before attaching them to agent nodes in Graph Studio.

## Where in the product

| Surface | Path |
| --- | --- |
| Workspace sidebar | **RAG Data** |
| URL | `/{org}/workspace/{workspaceId}/data-sources` |
| Collection detail | `.../data-sources/{datasourceId}` |

<Frame caption="RAG Data — workspace collections">
  <img src="/images/v2/rag/01-data-sources.png" alt="RAG Data list" />
</Frame>

## Create a data source

1. Open **RAG Data** from the workspace sidebar.
2. Create a new data source or open an existing collection.
3. Add files or connect ingestion sources supported by your deployment.
4. Wait for indexing to complete (status shown in the collection UI).
5. In Graph Studio, attach indexed items on the agent node **RAG** tab ([Referencing in agents](/graph-studio/rag-management/referencing)).

<Note>
  RAG Data is workspace-scoped; any Agent Graph in the workspace can reference allowed collections. Permission: `workspace.sidebar.datasources`.
</Note>

## Related

- [RAG Management](/graph-studio/rag-management)
- [Collections](/graph-studio/rag-management/collections)
- [Referencing RAG in agents](/graph-studio/rag-management/referencing)
