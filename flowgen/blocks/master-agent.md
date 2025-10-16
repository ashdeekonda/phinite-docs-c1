---
title: "Master Agent"
description: "The primary agent node that performs reasoning, RAG, and tool use."
---

## Configuration

- **Name**: human-readable label for the agent
- **Prompt**: main `task_prompt` defining behavior
- **Tools**: select workspace or predefined tools to enable actions
- **RAG**: attach data sources/collections to ground answers
- **Variables**: define input and capture variables
- **Decision Variables**: drive conditional edges downstream

<Note>
Implemented as the `task` node type in `src/components/nodes/task/` with configuration via `Details`, `RAG`, and `Variables` drawers.
</Note>
