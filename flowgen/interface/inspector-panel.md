---
title: "Inspector Panel"
description: "Configure the selected block’s prompts, RAG, tools, and variables."
---

## Inspector tabs

The Inspector appears when you select a block. It’s implemented as `NodeDrawer` in `studio/components/NodeDrawer.tsx`.

- **Details**: name, description, and main prompt (`task_prompt`)
- **RAG**: attach data sources and items to ground the agent
- **Variables**: manage input variables and capture variables
- **Decision**: choose variables used for conditional edges
- **Flow**: configure sub-flow parameters (for `flow` nodes)

<Tip>
Use the prompt refinement feature in Details to improve clarity and consistency before publishing.
</Tip>
