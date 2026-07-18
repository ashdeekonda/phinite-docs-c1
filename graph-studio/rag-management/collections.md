---
title: RAG collections
description: Curate documents and items inside a RAG data source.
---

A **collection** groups indexed **items** (documents, rows, or chunks) under a **RAG Data** source. Agents attach at the item level in the node drawer.

## Manage collections

1. Open **RAG Data** ([Data sources](/graph-studio/rag-management/data-sources)).
2. Select a data source to open its detail view.
3. Create or rename collections; add or remove items.
4. Confirm indexing status before attaching items in Studio.

<Tip>
  Use meaningful collection and item names — they appear in the Studio **RAG** tab selector.
</Tip>

## Attach to agents

After items are indexed:

1. Open **Graph Studio** → select a **Master Agent** or **Child Agent** node.
2. Open the **RAG** tab ([Referencing](/graph-studio/rag-management/referencing)).
3. Select the data source and items for that node only.
4. **Save** the graph.

## Related

- [RAG Data sources](/graph-studio/rag-management/data-sources)
- [Referencing in agents](/graph-studio/rag-management/referencing)
