---
title: Agent node anatomy
description: Prompt, RAG, tools, variables, and registry agents on Master and Child Agent nodes.
---

Every **Master Agent** and **Child Agent** node combines four core drawer areas plus optional **Browse** / **Discovery** registry attachments. Open the [Inspector (node drawer)](/graph-studio/interface/inspector-panel) by selecting a node on the canvas.

<CardGroup cols={2}>
  <Card title="Agent prompt" icon="file-lines" href="/graph-studio/agent-node/prompt">
    Task prompt and behavior in **Details**.
  </Card>
  <Card title="RAG" icon="book" href="/graph-studio/rag-management/referencing">
    Attach [RAG Data](/graph-studio/rag-management) collections per node.
  </Card>
  <Card title="Tools" icon="wrench" href="/graph-studio/agent-node/tools">
    Published tools and integrations for this step.
  </Card>
  <Card title="Variables" icon="database" href="/graph-studio/agent-node/variables">
    Input and capture variables for the step.
  </Card>
  <Card title="Registry agents (A2A)" icon="share-nodes" href="/agent-registry/registry-agent-nodes">
    **Browse** or **Discovery** on a Master Agent node.
  </Card>
</CardGroup>

## Master Agent vs Child Agent

| | **Master Agent** | **Child Agent** |
| --- | --- | --- |
| **Role** | Primary orchestrator for the graph | Delegated sub-task with its own prompt and tools |
| **When to use** | Default reasoning step; supports registry agents | Distinct specialist step in a large or multi-step graph |
| **Drawer tabs** | Details, Tools, RAG, Variables, Decision | Same, plus **Child Variables** where shown |
| **Registry agents** | **Browse** / **Discovery** attachments | Not available — attach via the Master Agent |

<Note>
  In the codebase the Master Agent is implemented as the `task` node with configuration via Details, RAG, and Variables drawers. Child agents do not replace the Master — the Master still orchestrates the overall run.
</Note>

## How components interact

```mermaid
flowchart LR
  input[InputVariables]
  rag[RAGKnowledge]
  tools[Tools]
  prompt[AgentPrompt]
  llm[LLMStep]
  capture[CaptureVariables]
  decision[DecisionVariables]

  input --> prompt
  rag --> prompt
  tools --> prompt
  prompt --> llm
  llm --> capture
  llm --> decision
```

## Configure an agent node

1. Add a **Master Agent** or **Child Agent** from the canvas toolbar ([Node types](/graph-studio/nodes)).
2. Select the node and complete drawer tabs: **Details** → **Tools** → **RAG** → **Variables**.
3. For branching, set **Decision** variables before [conditional edges](/graph-studio/connections/conditional-edges).
4. On Master Agents, optionally attach [registry agents](/agent-registry/registry-agent-nodes).
5. **Save** the graph.

<Note>
  Node configuration requires appropriate workspace permissions (typically Developer role or higher). See [User roles](/user-management/user-roles).
</Note>

## Related

- [Inspector (node drawer)](/graph-studio/interface/inspector-panel)
- [Node types](/graph-studio/nodes)
- [Graph Studio overview](/graph-studio/overview)
