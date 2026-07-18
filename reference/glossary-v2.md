---
title: Glossary
description: Current Phinite terms for the agent-first product model.
---

## Primary objects

| Term | Meaning |
| --- | --- |
| **Agent Graph** | The workflow you design in Graph Studio. Types: Conversational or Autonomous. |
| **Conversational** | Voice/chat agent for real-time user conversations. |
| **Autonomous** | Background agent for scheduled tasks, monitoring, and automation without a live user. |
| **Node** | Canvas building block (Start, Master Agent, Child Agent, Tool, End, registry agent). Legacy: Block. |
| **Build** | Immutable snapshot of an agent graph + pinned tool versions, ready to deploy. |
| **Environment** | DEV, UAT, or PROD — where a build runs and which env variables apply. |
| **Channel** | Messaging ingress (WhatsApp, Slack, Teams, web chat, voice, email, …) wired to a build. |
| **Trigger** | Webhook or schedule that starts an agent run (API, Cron, background task). |
| **Agent Card** | Public identity + metadata for an agent exposed over A2A (skills, tags, visibility). |
| **Agent Card version** | One expose registration; status **TEST** or **LIVE**. |
| **Agent Registry** | Workspace catalog of exposed A2A agents. |
| **Tool** | Callable integration or custom function used by nodes in an agent graph. |
| **RAG Data** | Workspace knowledge collections attached to agent nodes for retrieval. |

## A2A terms

| Term | Meaning |
| --- | --- |
| **Browse** | Registry agent node mode — calls one selected `a2aregistryid`. |
| **Discovery** | Registry agent node mode — runtime match using saved filters. |
| **TEST** | Agent Card / build status for validation URL (`.../a2a/{flowId}/{registryId}`). |
| **LIVE** | Production Agent Card; short URL (`.../a2a/{flowId}`). |
| **Discoverability Tags** | Metadata on Agent Card for search and Discovery filters. |
| **Skills** | Callable capabilities on Agent Card with input/output MIME modes. |

## Surfaces

| Surface | Where |
| --- | --- |
| **Workspace Home** | Agent Graphs list; create and open graphs |
| **Graph Studio** | Canvas to design nodes, tools, RAG, variables |
| **Tools** | Workspace tool library; **Open Dev Studio** edits tool code |
| **Dev Studio** | Tool code editor opened from Tools (not a separate nav root) |
| **Integrations** | Channels, Integration Tools, Triggers hub |
| **Env. variables** | DEV / UAT / PROD secrets and config |
| **RAG Data** | Workspace data sources and collections |
| **Model Keys** | BYOK provider keys (`workspace.sidebar.byok`) |
| **Agent Registry** | Browse exposed A2A agents |

## Configuration

| Term | Meaning |
| --- | --- |
| **Node config** | Prompt, tools, RAG, variables, model on a node drawer |
| **Build export** | Export tools/MCP/env into build or Agent Card version |
| **config_id** | Connected integration config on Browse registry nodes |

## Dead terms (do not use)

| Old term | Use instead |
| --- | --- |
| Assistant | Agent Graph (or Agent) |
| Flow / Flow Studio | Agent Graph / Graph Studio |
| Block | Node |
| DevStudio (nav label) | Tools |

## Deploy vs expose

| Path | Outcome |
| --- | --- |
| **Deploy to Channel** | Assign build to a channel environment + webhook |
| **Deploy as Chat API** | HTTP chat endpoint for apps/backends |
| **Deploy as API / Cron** | Autonomous trigger webhook or schedule |
| **Deploy as A2A** | Publish Agent Card → TEST → Push To Prod → LIVE URL |
