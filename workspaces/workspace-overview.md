---
title: "Workspace Overview"
description: "Understand how workspaces organize assistants, tools, integrations, and team collaboration in Phinite."
---

# Workspace Overview

A workspace is the central collaboration environment within Phinite. It brings together your assistants, tools, integrations, and collections in one place.

When you log in, you land on **Workspace Home** — a dashboard of your assistants with search, templates, and a **How to ship** guide that opens onboarding journeys for conversational, autonomous, and Agent Registry workflows.

> 1. Workspaces are typically created by the **Organization Owner (Super Admin)** and managed by **Admins**.
> 2. **Developers** and **QA** are added with controlled access through role-based permissions.

<Info>
  Workspaces help teams isolate projects, manage access levels, and reuse assets across assistants.
</Info>

---

## Workspace Home

Workspace Home includes:

- **My Assistants** and **Templates** tabs
- Search across assistants
- **New Assistant** (when permitted)
- **How to ship** — opens guided journeys for building and deploying assistants

Use **How to ship** beside the assistant tabs to walk through publish, channels, builds, and registry steps for your assistant type.

---

### Multi-Workspace Access

From the global header, switch between workspaces or create new ones if you have permission.

Super Admins can create additional workspaces and assign Admins to manage them.

![Create Workspace Gi](/images/create_workspace.gif)

---

## Sidebar Navigation

The workspace left sidebar is your main navigation panel:

| Section | What it does |
| --- | --- |
| **Workspace Home** | List and create assistants |
| **Tools** | Workspace-level tools reusable across assistants |
| **Agent Registry** | Browse, expose, and manage A2A Agent Cards |
| **Integrations** | **Channels** and **Predefined tools** tabs |
| **MCP Server** | Configure MCP servers for tools and expose flows |
| **Datasources** | Manage **Collections** for RAG (page title: Collections) |
| **API Keys** | Workspace API keys for triggers and external calls |
| **Model Keys** | Bring-your-own-key (BYOK) for LLM providers |
| **Observability** | **Sessions** list and session logs |
| **Users** | Invite and manage members (Admins) |
| **Billing & Usage** | Plan, usage, and invoices (Admins) |

Evaluations appears under assistant **Monitor** in the product UI and is marked **Coming soon** at the workspace level.

---

### Assistants

Assistants are conversational, email, or autonomous agents. Each assistant opens its own sidebar with **Build**, **Deploy**, and **Monitor** sections:

- **Build** — Overview, **Agent Graphs** (Graph Studio), **Tools** (Dev Studio), **Intents** or **Triggers** (by type)
- **Deploy** — **Builds**, **Env. variables**, **Agent Cards** (conversational/voice)
- **Monitor** — **Observability** (filtered to that assistant), Evaluations (coming soon)

Inside **Graph Studio**, use **Phinite Aura** (natural language) or manual editing to design agent graphs. Aura is not a separate app — it is the AI assistant panel in Graph Studio and Dev Studio.

---

### Workspace Tools

**Tools** at workspace scope are shared across assistants. Open an assistant's **Tools** list to attach them, or use **Dev Studio** to author and test tool logic.

---

### Integrations

Open **Integrations** in the sidebar. Two tabs:

1. **Channels** — Webchat, WhatsApp, Slack, Teams, Twilio, email, and related setup
2. **Predefined tools** — Connectors such as Gmail, Jira, Salesforce, and the full catalog

After you save a connection, predefined tools appear in Graph Studio's tool picker and in Dev Studio.

---

### Agent Registry

**Agent Registry** is the workspace catalog of agents exposed over the **Agent-to-Agent (A2A)** protocol.

- **Expose** published agent graphs as hosted endpoints
- **Browse** organisation and public Agent Cards
- **Compose** with registry agent nodes in Graph Studio (Browse or Discovery mode)

See [Agent Registry overview](/agent-registry/overview).

---

### Collections (Datasources)

The sidebar label is **Datasources**; the page title is **Collections**. Upload and organise knowledge for RAG — PDFs, text, and connected sources — then reference collections in agent nodes.

---

### API Keys and Model Keys

- **API Keys** — Trigger agent graphs, call platform APIs, and authenticate webhooks
- **Model Keys** — BYOK credentials for LLM providers used by Aura and agent nodes

---

### Users and roles

**Users** (Admins) invite members and assign **Admin**, **Developer**, or **QA** roles. See [User roles](/user-management/user-roles).

---

### Billing & Usage

**Billing & Usage** shows plan details, Aura and token consumption, telephony usage, and invoices.

---

### Observability

**Observability** opens the **Sessions** list — every assistant run with filters by channel, environment, and assistant. Drill into session logs for timeline, decision points, and variables.

---

## Header utilities

The top header includes **Docs**, **Support**, **Feedback**, and theme toggle. Documentation opens [docs.phinite.ai](https://docs.phinite.ai).

---

## Bottom navigation

At the bottom of the sidebar:

- **Workspace Settings** — Workspace name and preferences
- **Profile** — Personal settings and sign-out

---

## Summary

A workspace is your team's shared environment for assistants, integrations, collections, and observability — with RBAC so each role sees the right modules.

<Tip>
  Use one workspace per functional team or business unit for clarity and security.
</Tip>
