---
title: "Node types"
description: "Understand each node type used to compose Agent Graphs."
---

## Nodes overview

<Frame>
  <img src="/images/blocks.png" alt="Node types palette" />
</Frame>

- **Start**: graph entry; one source handle to begin execution
- **Master Agent**: core reasoning unit with prompt, tools, RAG, and variables
- **Child Agent**: reusable/embedded agent with its own variables and prompt
- **Tool**: external API/tool call node
- **Sub-Agent Graph**: reference and invoke another Agent Graph (optional)
- **End**: terminal node for completion

<a id="start-node"></a>

## Start node
- Non-deletable by default
- Only a source handle (no incoming edges)

<Info>
See `src/components/nodes/start/` for the implementation and styling.
</Info>

<a id="master-agent-node"></a>

## Master agent node
- **Name**: human-readable label for the agent
- **Prompt**: main `task_prompt` defining behavior
- **Tools**: select workspace or predefined tools to enable actions
- **RAG**: attach data sources/collections to ground answers
- **Variables**: define input and capture variables
- **Decision Variables**: drive conditional edges downstream

<Note>
Implemented as the `task` node type in `src/components/nodes/task/` with configuration via `Details`, `RAG`, and `Variables` drawers.
</Note>

<a id="child-agent-node"></a>

## Child agent node
- **Prompt**: behavior specific to the child agent
- **Child Variables**: input and capture variables managed separately
- **Tools & RAG**: optional, same as Master Agent when needed

<Info>
Rendered via `src/components/nodes/child/` with configuration in `drawer/ChildDetails.tsx` and `drawer/ChildVariables.tsx`.
</Info>

<a id="tool-node"></a>

## Tool node
- **Tool selection**: choose the tool or sub-tool to invoke
- **Inputs**: map variables to tool parameters
- **Outputs**: expose results for downstream steps

<Note>
Implemented as the `api` node type in `src/components/nodes/api/`. Tool metadata is sourced from your workspace tools.
</Note>

<a id="end-node"></a>

## End node
- Non-deletable by default
- Only accepts incoming edges
- Use multiple End nodes to represent distinct terminal outcomes
