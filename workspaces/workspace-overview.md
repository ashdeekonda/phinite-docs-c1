---
title: Workspace overview
description: How workspaces organize Agent Graphs, tools, integrations, and team collaboration in Phinite.
icon: building
---

A **workspace** is the central collaboration environment in Phinite. It brings together your **Agent Graphs**, tools, integrations, and data sources into one governed space.

When you log in, you land on **Workspace Home** — your dashboard for creating and opening Agent Graphs.

<CardGroup cols={2}>
  <Card title="About Phinite" icon="book-open" href="/getting-started/about-phinite">
    Platform overview and golden path.
  </Card>
  <Card title="Agent Graphs" icon="diagram-project" href="/agents/overview">
    Conversational vs Autonomous graph types.
  </Card>
  <Card title="User roles" icon="users" href="/user-management/user-roles">
    RBAC for developers, admins, and testers.
  </Card>
  <Card title="Inviting users" icon="user-plus" type="note" href="/user-management/inviting-users">
    Add teammates to a workspace.
  </Card>
</CardGroup>

<Info>
  Workspaces help teams isolate projects, manage access levels, and reuse tools and integrations across Agent Graphs within a common environment.
</Info>

## Workspace Home

Workspace Home provides a quick overview of your Agent Graphs and workspace-level activity.

| Element | Description |
| --- | --- |
| Agent Graph list | Grid or list of existing graphs with type and status |
| **New Agent Graph** | Create Conversational or Autonomous graphs |
| **Phinite Aura** | Optional copilot launcher for natural-language graph creation |
| Metrics | Usage analytics for your plan (when enabled) |

<Frame caption="Workspace Home — Agent Graph list and create entry point">
  <img src="/images/v2/agents/00-workspace-home.png" alt="Workspace Home with Agent Graph cards" />
</Frame>

<Note>
  Depending on workspace configuration, the home page may also display activity logs, performance charts, or project summaries.
</Note>

## Multi-workspace access

From the global header, switch between workspaces or create new ones if you have permission.

1. Click the workspace name in the header.
2. Select an existing workspace or **Create workspace** (Super Admin / Admin).
3. Super Admins can assign Admins to manage each workspace independently.

<Frame caption="Create workspace — organization-level setup">
  <img src="/images/create_workspace.gif" alt="Create workspace flow" />
</Frame>

<Check>
  If you see multiple workspaces in the dropdown, your organization supports multi-workspace collaboration.
</Check>

## Sidebar navigation

Each workspace sidebar is your main navigation panel.

### Agent Graphs

**Agent Graphs** are the core objects in a workspace. Create **Conversational** or **Autonomous** graphs from Workspace Home, then open each graph in:

| Surface | Purpose |
| --- | --- |
| **Graph Studio** | Visual workflow design — Save, Build, Deploy, Test |
| **Tools & Dev Studio** | Custom and prebuilt tool development |
| **Phinite Aura** | Natural-language graph edits in Studio |

Agent Graphs in a workspace share tools, integrations, and RAG Data collections.

<Tip>
  Use consistent naming conventions (for example `support-faq-conv`, `nightly-etl-auto`) to group related graphs.
</Tip>

### Tools

Workspace **Tools** are reusable components any Agent Graph can call at runtime:

- Custom Python handlers
- Prebuilt integration subtools
- System tools and utility functions

Open **Dev Studio** from any tool to edit code, test, and publish versions. See [Tools & Dev Studio overview](/devstudio/overview).

### Integrations

Integrations connect your workspace to external systems and communication channels.

| Type | Examples |
| --- | --- |
| **Predefined integrations** | Jira, Gmail, Salesforce, HubSpot |
| **Channel integrations** | WhatsApp, Slack, Teams, Twilio, email |

Authenticate once under **Integrations**, then wire channels and triggers to deployed builds. See [Configure integrations](/configure/integrations) and [Channels overview](/channels/overview).

### Agent Registry

**Agent Registry** is the workspace catalog of agents exposed over the **Agent-to-Agent (A2A) protocol**. Open it from the sidebar when your organisation grants `workspace.sidebar.agent_registry`.

Use it to:

- **Expose** published agent graphs as hosted A2A endpoints
- **Browse** organisation and public Agent Cards
- **Compose** multi-agent flows with registry agent nodes in Graph Studio

See [Agent Registry overview](/agent-registry/overview).

### RAG Data

**RAG Data** manages workspace knowledge collections used by agent nodes for retrieval.

Supported sources include PDF, CSV, text documents, structured datasets, and API-connected endpoints. Organize content into collections referenced in [Graph Studio RAG settings](/graph-studio/rag-management).

### Env. variables

**Env. variables** store DEV / UAT / PROD secrets and configuration. Tools and builds read these at runtime — never hard-code credentials in tool code. See [Env. variables](/configure/env-variables).

### API Keys

Generate workspace-level API keys for programmatic access:

- Trigger Agent Graph runs from external applications
- Authenticate Chat API and trigger webhooks
- Regenerate or revoke keys as needed

<Warning>
  Treat API keys as confidential credentials. Revoking a key immediately disables all external requests using that key.
</Warning>

### Users

Admins and Organization Owners manage workspace members — invite users, assign roles, or remove access.

| Role | Scope |
| --- | --- |
| **Super Admin** | Full platform access |
| **Admin** | Workspace management, billing, user access |
| **Developer** | Build and test Agent Graphs and tools |
| **Tester (QA)** | Validate workflows and review logs |

See [Access controls](/user-management/access-controls) and [User roles](/user-management/user-roles).

### Billing and reports

**Billing** (Organization Owners) shows plan details, usage metrics (tokens, compute, voice minutes), and invoices.

**Reports** provide session activity, token consumption, and graph-level execution summaries filterable by environment (DEV, UAT, PROD). Data integrates with [Observability](/observability/overview).

## Bottom navigation

| Item | Purpose |
| --- | --- |
| **Workspace Settings** | Name, environment configuration, preferences |
| **Documentation** | Link to Phinite docs |
| **User Profile** | Personal details, preferences, sign-out |

## Summary

A workspace is your team's shared environment where Agent Graphs, integrations, and data sources coexist with governance, modularity, and role-based collaboration.

<Tip>
  Use one workspace per functional team or business unit to maintain clarity, security, and scalable growth.
</Tip>
