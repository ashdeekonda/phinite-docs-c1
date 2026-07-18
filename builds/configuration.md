---
title: Build configuration
description: Pin graph and tool versions, export integrations, and set environment-specific options.
---

**Build configuration** covers what gets frozen into an **Agent Build**: the **Agent Graph** version, **tool** versions, optional exported **MCP** / **env** values, and runtime settings resolved per **environment**.

<Note>
  Do not hardcode secrets on the canvas. Use **Env. variables** ([Environments](/builds/environments)) and reference keys by name in tools and nodes.
</Note>

## Build Agent dialog fields

| Section | Purpose |
| --- | --- |
| **Description** | Human-readable build notes for your team |
| **AGENT GRAPH** | Which saved graph version to freeze |
| **TOOLS** | Published tool versions linked to the graph — **Publish** inline if needed |

<Frame caption="Build Agent form — graph version and tool pinning">
  <img src="/images/v2/builds/03-build-form.png" alt="Build Agent configuration form" />
</Frame>

## Create a configured build

1. **Save** the Agent Graph in Graph Studio.
2. Click **Build** and wait for validation.
3. Enter a **Description**.
4. Confirm the **AGENT GRAPH** accordion shows the intended version.
5. In **TOOLS**, select published versions — publish any tool still in draft.
6. Click **Create Build**.

## Export additional config (A2A and advanced builds)

When exposing over A2A or bundling integrations for external callers, use the export step in the **Expose as External Agent** wizard or the equivalent **Build** export toggle:

1. Enable **Export value for agent version** (Expose step 2) or the build export option.
2. Use tabs **Predefined**, **MCP**, and **Env** — search **Search tools and variables...**
3. For each exported row, provide a required **description**.
4. Continue to **Agent Card** or **Create Build**.

<Frame caption="Build export — pin tools, MCP, and env into the build snapshot">
  <img src="/images/v2/configure/02-build-export.png" alt="Export tools and variables in build dialog" />
</Frame>

See [Build export configuration](/configure/build-export) for the full Expose wizard path.

## Environment-specific runtime

Builds read configuration at runtime based on the assigned **environment**:

| Setting | Source |
| --- | --- |
| API endpoints and credentials | **Env. variables** DEV / UAT / PROD columns |
| Channel / trigger webhooks | Per-environment URLs from Integrations |
| Tool credentials | Published tool config + exported build rows |
| Rate limits and quotas | Platform and workspace policy |

## When to export into a build

- External A2A callers need tool credentials bundled with the Agent Card version.
- Registry **Browse** nodes require `config_id` and satisfied tool/env on the registration build.
- A trigger or channel deploy must carry MCP connections not already on the graph.

## Related

- [Builds overview](/builds/overview)
- [Build export](/configure/build-export)
- [Build environments](/builds/environments)
- [Expose your flow](/agent-registry/expose-your-flow)
