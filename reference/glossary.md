---
title: "Glossary of Terms"
description: "Common terminology used throughout Phinite."
icon: book
---

## Terms

- **Assistant**: An AI capability (Conversational, Email, Autonomous) powered by agent graphs
- **Agent Graph**: Visual orchestration of agent nodes, edges, variables, and logic in Graph Studio (not a linear "flow")
- **Agent node**: An LLM-driven node with prompt, tools, variables, and RAG on the canvas
- **Phinite Aura**: AI assistant in Graph Studio and Dev Studio for building and editing agent graphs and tools
- **Collections**: Workspace knowledge stores (sidebar: **Datasources**) used for RAG retrieval
- **Tool**: Reusable capability that performs external actions
- **RAG**: Retrieval-Augmented Generation; attaches knowledge collections
- **Intent**: Classification of user utterance that maps to an agent graph path (conversational/email assistants)
- **Trigger**: Event that starts an agent graph (webhook, cron, email) on autonomous assistants
- **Build**: Versioned package of agent graphs and tools for deployment
- **Environment**: Dev, UAT, or Production runtime context
- **Session**: A single interaction run (chat, call, or execution); primary row in Observability → Sessions
- **Token**: Unit of LLM usage for cost/usage tracking
- **A2A (Agent-to-Agent)**: Workspace catalog of Agent Cards and hosted endpoints — see [A2A glossary](/agent-registry/glossary)
- **Agent Card**: Registered metadata (skills, tags, visibility) for an exposed agent graph build
- **A2A (Agent-to-Agent)**: Protocol for agents to discover and call each other via hosted endpoints
