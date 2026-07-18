---
title: "JiraTools"
description: "Create, search, update, comment on, and transition Jira issues from Agent Graph nodes."
icon: "ticket"
---

**JiraTools** wraps common Jira Cloud/Server REST operations for support, ops, and engineering Agent Graphs.

<Card title="Predefined tools hub" icon="plug" href="/devstudio/prebuilt-tools">
  Full prebuilt catalog and quick-start steps.
</Card>

## Required configuration

| Field | Type | Notes |
| --- | --- | --- |
| `server_url` | string | Base URL (for example `https://yourdomain.atlassian.net`) |
| `username` | string | Account email or username |
| `token` | string | API token (preferred for Cloud) |

## Setup

1. Generate a Jira API token for the service account your graph will use.
2. Add **JiraTools** on an agent node and create a connection with the fields above.
3. Enable subtools (`get_issue`, `create_issue`, `search_issues`, etc.) needed by your prompt.
4. Test `get_projects` or `search_issues` with a narrow JQL query, then **Save**.

## Subtools

`get_issue`, `create_issue`, `search_issues`, `add_comment`, `update_issue`, `transition_issue`, `get_projects`

<Warning>
  JQL results respect Jira permissions—if a user cannot view an issue in the UI, the tool cannot fetch it either.
</Warning>

## Related

- [Jira integration hub](/integrations-hub/jira)
