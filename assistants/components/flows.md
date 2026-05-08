---
title: "Agent Graphs"
description: "The orchestration layer powering assistants with logic, agents, and tools."
---

## Overview

<Frame>
  ![Agent Graph](/images/Flow.png)
</Frame>

Agent Graphs are the heart of every Assistant. They define logic, decisions, and outcomes through nodes on a visual canvas. Agent Graphs are designed and maintained in [Graph Studio](/graph-studio/overview). Assistants execute Agent Graphs to deliver outcomes.

## Key concepts

- Nodes: Start, Agent, Tool, End
- RAG and Tools within Agent nodes
- Variables and Conditional Edges

### Anatomy of a Agent Graph

- **Start Node** — entry point connected to a Trigger or Intent.
- **Agent Nodes** — actions or messages the AI agent performs.
- **Tool nodes** — invoke custom tools or APIs.
- **Decision nodes** — define conditional logic paths.
- **Connector nodes** — move data between subgraphs or external systems.

<Note>
  Agent Graphs are saved automatically in real time. You can preview, test, and version them without deploying.
</Note>

### Using Copilot in Graph Studio

- Describe the goal in natural language.
- Copilot generates a full graph layout with connections and node suggestions.
- You can review and modify before saving.

### Debugging Agent Graphs

- Always validate input/output connections before saving.
- Use the **Preview Run** to simulate execution.
- Check the **Execution Logs** in the environment for variable mismatches or failed tool calls.

---

## Best practices

- Keep flows modular
- Reuse Child Agents for common patterns
- Use variables consistently for data passing