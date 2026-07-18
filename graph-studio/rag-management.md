---
title: RAG Management
description: Workspace RAG Data collections and attaching knowledge to agent nodes.
---

**RAG** (retrieval-augmented generation) grounds agent answers in your documents and structured data. Phinite splits this into two layers:

1. **RAG Data** — workspace collections you create once under **RAG Data** in the sidebar.
2. **Node attachment** — each **Master Agent** or **Child Agent** selects which collections/items to use at runtime.

<CardGroup cols={2}>
  <Card title="RAG Data sources" icon="folder" href="/graph-studio/rag-management/data-sources">
    Create and index collections in the workspace.
  </Card>
  <Card title="Collections" icon="layers" href="/graph-studio/rag-management/collections">
    Organize documents and items inside a data source.
  </Card>
  <Card title="Attach to agents" icon="link" href="/graph-studio/rag-management/referencing">
    Select sources in the node drawer **RAG** tab.
  </Card>
</CardGroup>

## High-level flow

1. Open workspace **RAG Data** and create or index a collection ([Data sources](/graph-studio/rag-management/data-sources)).
2. In **Graph Studio**, select an agent node → **RAG** tab ([Referencing](/graph-studio/rag-management/referencing)).
3. Choose data sources and items for that step only.
4. **Save** the graph; attachments pin with the graph version on **Build**.

<Frame caption="Workspace RAG Data — collections list">
  <img src="/images/v2/rag/01-data-sources.png" alt="RAG Data workspace page" />
</Frame>

## Related

- [Agent node RAG tab](/graph-studio/agent-node/rag)
- [Graph Studio overview](/graph-studio/overview)
