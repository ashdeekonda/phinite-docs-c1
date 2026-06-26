---
title: "Predefined Tools"
description: "Connect third-party APIs once under Integrations, then enable subtools per agent in Graph Studio."
icon: "plug"
---

Predefined tools are pre-packaged integrations (Gmail, Slack, Jira, Salesforce, MongoDB, and [80+ more](/integrations-hub/overview)) that you configure once in the workspace and reuse across assistants.

<Note>
  **Predefined tools live under Integrations**, not DevStudio. DevStudio is for building **custom tools**. Use this guide for the connect-once, use-everywhere workflow; use each integration's page for credentials and subtools.
</Note>

---

## Where to find them

In your workspace sidebar: **Integrations → Predefined tools**.

Browse the full catalog on the [Integrations overview](/integrations-hub/overview) page, organized by category (CRM, messaging, databases, payments, and more).

---

## How predefined tools work

| Concept | Description |
| --- | --- |
| **Connection** | Saved credentials (tokens, API keys, URLs) reusable across assistants |
| **Subtool** | Individual capability you enable per agent (e.g. `send_email`, `create_issue`) |
| **Tool picker** | After a connection exists, the tool appears in Graph Studio's agent node **Tools** tab |

---

## Quick start

<Steps>
  <Step title="Add a connection">
    Go to **Integrations → Predefined tools**, pick an integration (e.g. Gmail), click **+ Add Configuration**, enter credentials, and save.
  </Step>
  <Step title="Assign to assistants">
    Select which assistants may use the connection when saving.
  </Step>
  <Step title="Enable in Graph Studio">
    Open an agent node → **Tools** tab → **Add a new tool** → choose the predefined tool → select your connection → enable the subtools you need.
  </Step>
  <Step title="Test">
    Run a minimal subtool call (e.g. list channels, fetch one email) before attaching to a build.
  </Step>
</Steps>

> Tip: Request only the permissions each agent needs. A read-only email agent should not enable send or delete subtools.

---

## Generic configuration concepts

These apply to most predefined tools:

- **Required field** — Must be supplied to create or validate the connection
- **Optional field** — Finer control; can be omitted
- **Timeout** — Seconds to wait for a response; lower for interactive agents, higher for batch jobs
- **Headers** — Custom HTTP headers for API-based tools
- **Scopes / permissions** — OAuth or token scopes; request only what you need

---

## Predefined tools vs custom tools

| | Predefined tools | Custom tools (DevStudio) |
| --- | --- | --- |
| **Built by** | Phinite — ready-made integrations | Your team — business-specific logic |
| **Configured in** | Integrations → Predefined tools | DevStudio → Tools |
| **Best for** | Standard SaaS APIs (CRM, email, chat) | Proprietary APIs, complex transformations |
| **Docs** | [Integrations catalog](/integrations-hub/overview) | [DevStudio overview](/devstudio/overview) |

---

## Related topics

- [Integrations overview](/integrations-hub/overview) — full predefined tools catalog
- [Connecting tools to agents](/devstudio/linking-tools) — wire tools in Graph Studio
- [Custom tools](/devstudio/custom-tools) — build your own in DevStudio
- [Tool types](/devstudio/types) — custom, system, structure, and predefined
