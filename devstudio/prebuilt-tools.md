---
title: Predefined tools
description: Connect third-party APIs once, enable subtools on Agent Graph nodes — full catalog in Integrations Hub.
---

**Predefined tools** are platform-packaged integrations (Gmail, Jira, Salesforce, MongoDB, and dozens more). They are **not** authored in Dev Studio.

<Note>
  Save a **connection** under workspace **Integrations**, then enable **subtools** on agent nodes in Graph Studio.
</Note>

## How they work

| Concept | Meaning |
| --- | --- |
| **Connection** | Saved credentials reusable across Agent Graphs |
| **Subtool** | One callable action you enable per node |
| **Tools tab** | Where the graph selects connection and subtools |

<Frame caption="Workspace Integrations — predefined tools">
  <img src="/images/available-integrations.png" alt="Predefined integrations" className="dark:hidden" />
  <img src="/images/workspace-tools.png" alt="Predefined integrations dark" className="hidden dark:block" />
</Frame>

## Quick start

1. **Integrations** → **Predefined tools** ([configure integrations](/configure/integrations)).
2. Select vendor → **Add Configuration** → **Save**.
3. [Graph Studio](/graph-studio/agent-node) → **Tools** tab → pick integration → enable subtools.
4. **Save** → **Build**.

## Examples

### Gmail

1. **Integrations** → **Gmail** → `email` + `app_password`.
2. Graph Studio → **GmailTool** → enable `get_unread_emails` or `send_email`.

<Card title="Gmail reference" icon="envelope" href="/integrations-hub/gmail">
  Credentials, subtools, and setup.
</Card>

### Jira

1. **Integrations** → **Jira** → `server_url`, `username`, API `token`.
2. Graph Studio → **JiraTools** → enable `search_issues`, `create_issue`, etc.

<Card title="Jira reference" icon="ticket" href="/integrations-hub/jira">
  Credentials, subtools, and JQL workflows.
</Card>

## Full catalog

<CardGroup cols={2}>
  <Card title="Integrations Hub" icon="plug" href="/integrations-hub/overview">
    All predefined tools and channels by category.
  </Card>
  <Card title="Custom tools" icon="screwdriver-wrench" href="/devstudio/custom-tools">
    When no predefined integration fits.
  </Card>
</CardGroup>

<Tip>
  Enable only the subtools each graph needs — least privilege.
</Tip>

## Related

- [Tools & Dev Studio overview](/devstudio/overview)
- [Configure integrations](/configure/integrations)
