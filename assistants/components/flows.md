---
title: "Flows"
description: "The orchestration layer powering assistants with logic, agents, and tools."
---

## Overview
<Frame>
  <img src="/Ne-flow.png" alt="Flows" />
</Frame>


Flows are the heart of every Assistant. They define logic, decisions, and outcomes through blocks on a visual canvas.Flows are designed and maintained in [Flowgen Studio](/flowgen/overview). Assistants execute flows to deliver outcomes.

## Key concepts

- Blocks: Start, Agent, Tool, End
- RAG and Tools within Agent blocks
- Variables and Conditional Edges

### Anatomy of a Flow

- **Start Node** — entry point connected to a Trigger or Intent.
- **Agent Blocks** — actions or messages the AI agent performs.
- **Tool Blocks** — invoke custom tools or APIs.
- **Decision Blocks** — define conditional logic paths.
- **Connector Blocks** — move data between subflows or external systems.


<Note>
 Flows are saved automatically in real time. You can preview, test, and version them without deploying.
</Note>

### Using Copilot in Flowgen Studio

- Describe the goal in natural language.
- Copilot generates a full flow layout with connections and block suggestions.
- You can review and modify before saving.

### Debugging Flows

- Always validate input/output connections before saving.
- Use the **Preview Run** to simulate execution.
- Check the **Execution Logs** in the environment for variable mismatches or failed tool calls.

---

## Best practices

- Keep flows modular
- Reuse Child Agents for common patterns
- Use variables consistently for data passing