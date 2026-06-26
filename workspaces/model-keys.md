---
title: "Model Keys (BYOK)"
description: "Bring your own LLM API keys for Phinite Aura and agent nodes."
---

# Model Keys (BYOK)

**Model Keys** (sidebar label) let you add **bring-your-own-key (BYOK)** credentials for LLM providers used by **Phinite Aura**, agent nodes, and orchestration models.

## What it is for

- Use your organisation's API keys instead of platform-managed models
- Control cost and data residency for LLM calls
- Select models per agent node from keys configured here

## Where to configure

1. Open your workspace sidebar → **Model Keys**
2. Add a provider key following the in-app instructions
3. In Graph Studio, pick the model and key in the agent node inspector (**Orchestration model**)

## Access

Requires `workspace.sidebar.byok` (or equivalent) permission. Admins and Developers typically configure keys; QA may have read-only access depending on role setup.

## Related

- [API Keys](/workspaces/workspace-overview#api-keys-and-model-keys)
- [Workspace overview](/workspaces/workspace-overview)
- [Graph Studio — agent node](/graph-studio/agent-node)
