---
title: Build export configuration
description: Export tools, MCP, and env variables into builds and Agent Card versions.
---

## What this is

When you **Build** or **Expose as A2A**, you can export additional **tools**, **MCP** connections, and **environment variables** into the immutable build snapshot. This ensures the deployed agent or Agent Card version carries the integrations callers need.

## Where in the product

| Wizard | Step | UI label |
| --- | --- | --- |
| **Build Agent** | After graph + tools review | Tool version pinning; unpublished tools show **Publish** |
| **Expose as A2A** | Step 2 (before Agent Card) | **Export value for agent version** — tabs **Predefined**, **MCP**, **Env** |
| **Expose as A2A** | Step 3 | **Agent Card** identity ([Agent Card identity](/a2a/agent-card-identity)) |

![Build Agent form](/images/v2/configure/02-build-export.png)

## Steps — Build wizard

1. Click **Build** in Graph Studio (graph must be **Saved**).
2. Wait for validation and the **Build Agent** form.
3. Add a **Description**.
4. Confirm **AGENT GRAPH** version and **TOOLS** — publish any tool showing **Publish**.
5. Click **Create Build**.

## Steps — export in Expose wizard

1. Start **Deploy** → **Deploy as A2A** (or expose flow from Agent Builds).
2. Complete **Agent Build Config** (graph + tools).
3. On the export step, enable **Export value for agent version**.
4. Use tabs **Predefined**, **MCP**, **Env** and search **Search tools and variables...**
5. For each exported row, provide a **description** (required).
6. Continue to **Agent Card** step and submit.

## When to export

- External A2A callers need tool credentials bundled with the Agent Card version.
- Registry **Browse** nodes require `config_id` and satisfied tool/env on the registration build.

## Related

- [Builds](/agents/builds)
- [Agent Card identity](/a2a/agent-card-identity)
- [Env. variables](/configure/env-variables)
- [Expose as A2A](/agents/expose-a2a)
