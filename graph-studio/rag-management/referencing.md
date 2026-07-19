---
title: Referencing RAG in agents
description: Attach RAG collections and items in the agent node drawer.
---

After you create **RAG Data** collections, attach them to specific **Master Agent** or **Child Agent** nodes so only that step retrieves those sources during a run.

## Where in the product

| Surface | Path |
| --- | --- |
| Graph Studio | Open Agent Graph → select agent node |
| Node drawer | **RAG** tab |
| Manage collections | Links from drawer open `.../data-sources/{id}` |

<Frame caption="Node drawer — RAG tab with data source and item selection">
  <img src="/images/v2/rag/02-node-rag-drawer.png" alt="RAG tab on agent node" />
</Frame>

## Attach RAG to a node

1. Open **Graph Studio** and select the target Agent Graph.
2. Click a **Master Agent** or **Child Agent** node.
3. Open the **RAG** tab in the node drawer.
4. Select a **data source** and the **items** (documents / rows) to include.
5. Optionally open **RAG Data** from the drawer to manage collections.
6. Click **Save** on the canvas toolbar.

## Runtime and builds

Attached RAG lists are saved with the graph version. When you **Build**, the pinned graph version includes those attachments for deploy.

<Info>
  See [RAG Management overview](/graph-studio/rag-management) for the two-layer model (workspace data vs node attachment).
</Info>

## Related

- [RAG Data sources](/graph-studio/rag-management/data-sources)
- [Agent configuration](/graph-studio/agent-node)
- [Builds](/builds/overview)
