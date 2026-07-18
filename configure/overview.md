---
title: Configuration overview
description: All configuration layers — node, env, integrations, and build export.
---

## What this is

**Configuration** in Phinite spans several surfaces. Each layer applies at a different stage of design → build → deploy.

## Configuration layers

| Layer | Where | When it applies |
| --- | --- | --- |
| **Node config** | Graph Studio node drawer (prompt, tools, RAG, variables, model) | While designing the Agent Graph |
| **Env. variables** | Workspace **Env. variables** (DEV / UAT / PROD) | Runtime secrets per environment |
| **Integrations** | Workspace **Integrations** + Studio **Integrations** / **Triggers** | Channel webhooks, triggers, app tools |
| **Build export** | **Build** and **Expose as A2A** wizards | Pin tool/env/MCP into immutable build or Agent Card version |

## Where in the product

| Surface | Path |
| --- | --- |
| Graph Studio | `.../studio?flowId=...` |
| Env. variables | `.../environment` |
| Integrations hub | `.../integration?tab=channels\|triggers\|predefined-tools` |
| Build / Deploy | Studio toolbar **Build**, **Deploy** |

## Typical order

1. Configure nodes in Studio ([Nodes](/studio/nodes), [Variables](/studio/variables), [RAG](/rag/overview)).
2. Set **Env. variables** for DEV / UAT / PROD.
3. Connect **Integrations** (channels, triggers, tools).
4. **Build** — pin versions; optionally [export config to build](/configure/build-export).
5. **Deploy** or **Expose as A2A**.

## Related

- [Env. variables](/configure/env-variables)
- [Integrations](/configure/integrations)
- [Build export](/configure/build-export)
- [Builds](/agents/builds)
