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