---
title: Model Keys
description: BYOK provider keys and model selection for agent nodes.
---

## What this is

**Model Keys** let you bring your own provider credentials (BYOK) or use the platform **Phinite Key**. Agent nodes select which model and key to use for LLM calls.

## Where in the product

| Surface | Path |
| --- | --- |
| Workspace **Keys** pocket | **Model Keys** |
| URL | `/{org}/workspace/{workspaceId}/model-key` |
| Per-node model | Graph Studio → agent node drawer → model / provider fields |

![Model Keys](/images/v2/workspace/01-model-keys.png)

## Steps — workspace keys

1. Open **Keys** in the workspace sidebar (bottom section).
2. Click **Model Keys**.
3. Add a provider key or use the default **Phinite Key** card.
4. Set which key is default for the workspace if prompted.

## Steps — use on a node

1. Open **Graph Studio** and select a **Master Agent** or **Child Agent** node.
2. In the node drawer, choose **model** and provider settings.
3. Pick a key that matches your BYOK setup.
4. **Save** the graph before **Build**.

## Permissions

- Model Keys: `workspace.sidebar.byok`

## Related

- [Node types](/studio/nodes)
- [Build an agent graph](/agents/build-graph)
- [Configuration overview](/configure/overview)
