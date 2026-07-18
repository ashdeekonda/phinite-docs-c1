---
title: Attach RAG to nodes
description: Select RAG collections and items in the agent node drawer.
---

## What this is

After you create **RAG Data** collections, attach them to specific **Master Agent** or **Child Agent** nodes so only that step retrieves those sources during a run.

## Where in the product

| Surface | Path |
| --- | --- |
| Graph Studio | Open Agent Graph → select agent node |
| Node drawer | **RAG** tab |
| Deep link to collection | Links from drawer open `.../data-sources/{id}` |

![RAG tab on node](/images/v2/rag/02-node-rag-drawer.png)

## Steps

1. Open **Graph Studio** and select the target Agent Graph.
2. Click a **Master Agent** or **Child Agent** node.
3. Open the **RAG** tab in the node drawer.
4. Select a **data source** and the **items** (documents / rows) to include.
5. Optionally open **RAG Data** from the drawer to manage collections.
6. Click **Save** on the canvas toolbar.

## Runtime

Attached RAG lists are saved with the graph version. When you **Build**, the pinned graph version includes those attachments for deploy.

## Related

- [RAG Data sources](/rag/data-sources)
- [Node types](/studio/nodes)
- [Builds](/agents/builds)
