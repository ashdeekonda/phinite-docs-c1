---
title: "Predefined Tools"
description: "Connect third-party APIs once, enable subtools on Agent Graph nodes — full vendor catalog in Integrations Hub."
---

**Predefined tools** are platform-packaged integrations (Gmail, Jira, Salesforce, MongoDB, and dozens more). You save a **connection** under workspace **Integrations**, then enable **subtools** on agent nodes in Graph Studio — the same pattern as [linking custom tools](/devstudio/linking-tools), without writing Python in Dev Studio.

<Note>
  Predefined tools are **not** authored in Dev Studio. Dev Studio is for **custom** and **Copilot-generated** handlers. Use this page for the workflow; use the [Integrations Hub](/integrations-hub/overview) for per-vendor credentials, subtools, and examples.
</Note>

## How predefined tools work

| Concept | Meaning |
| --- | --- |
| **Connection** | Saved credentials (OAuth, API token, connection string) reusable across Agent Graphs |
| **Subtool** | One callable action (for example `get_unread_emails`, `create_issue`) you enable per node |
| **Tool node / agent Tools tab** | Where the graph selects which connection and subtools run at runtime |

<Frame caption="Workspace Integrations — connect predefined tools once per workspace">
  <img src="/images/available-integrations.png" alt="Predefined tool integrations list" className="dark:hidden" />
  <img src="/images/workspace-tools.png" alt="Predefined tool integrations list dark mode" className="hidden dark:block" />
</Frame>

## Quick start

1. Open workspace **Integrations** → **Predefined tools** ([configure integrations](/configure/integrations)).
2. Select a vendor → **Add Configuration** → enter required credentials → **Save**.
3. In [Graph Studio](/graph-studio/overview), open an agent node **Tools** tab → **Add tool** → pick the integration.
4. Choose your saved **connection** (or add one inline) and enable only the **subtools** this graph needs.
5. **Save** the graph, [test](/devstudio/testing-tools) a call, then **Build** to pin the tool versions.

<Tip>
  Grant least privilege — a read-only email triage graph should not enable send or delete subtools.
</Tip>

## Examples

Two common patterns. Every other vendor follows the same connect → enable subtools → Build flow; see the full catalog in Integrations Hub.

### Gmail — inbox automation

Use when an Agent Graph reads, searches, or sends email.

1. **Integrations** → **Gmail** → add `email` and `app_password` (Google App Password).
2. Graph Studio → agent **Tools** → **GmailTool** → enable `get_unread_emails` or `send_email` as needed.

<Card title="Gmail — full reference" icon="envelope" href="/integrations-hub/gmail">
  Credentials, all 11 subtools, setup steps, and request examples.
</Card>

### Jira — issue automation

Use when an Agent Graph creates, searches, or transitions issues.

1. **Integrations** → **Jira** → add `server_url`, `username`, and API `token`.
2. Graph Studio → agent **Tools** → **JiraTools** → enable `search_issues`, `create_issue`, etc.

<Card title="Jira — full reference" icon="ticket" href="/integrations-hub/jira">
  Credentials, subtools, JQL search, and transition workflows.
</Card>

## Full vendor catalog

The **Integrations Hub** tab lists every predefined tool and channel — CRM, support, analytics, databases, payments, and more — each with its own credentials and subtool reference.

<CardGroup cols={2}>
  <Card title="Integrations Hub" icon="plug" href="/integrations-hub/overview">
    Browse all predefined tools and channels by category.
  </Card>
  <Card title="Configure integrations" icon="sliders" href="/configure/integrations">
    Workspace hub for channels, tools, and triggers.
  </Card>
  <Card title="Link tools to nodes" icon="link" href="/devstudio/linking-tools">
    Attach published custom or predefined tools on the canvas.
  </Card>
  <Card title="Custom tools" icon="screwdriver-wrench" href="/devstudio/custom-tools">
    When no predefined integration fits, author Python in Dev Studio.
  </Card>
</CardGroup>
