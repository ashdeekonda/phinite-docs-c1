---
title: Agent node RAG
description: Attach RAG Data sources and items in the node drawer RAG tab.
---

Use the drawer **RAG** tab to ground a specific **Master Agent** or **Child Agent** step with workspace knowledge.

<Frame caption="RAG tab — select data source and items">
  <img src="/images/v2/rag/02-node-rag-drawer.png" alt="RAG tab in node drawer" />
</Frame>

## Attach RAG

1. Create and index collections in [RAG Data](/graph-studio/rag-management/data-sources).
2. In Graph Studio, select an agent node.
3. Open **RAG** → choose **data source** and **items**.
4. **Save** the graph.

<Note>
  Attach only collections relevant to this step — narrower retrieval improves answer quality.
</Note>

## Full guide

See [Referencing RAG in agents](/graph-studio/rag-management/referencing) for workspace paths, runtime behavior, and build pinning.

## Related

- [RAG Management](/graph-studio/rag-management)
- [Agent node anatomy](/graph-studio/agent-node)
