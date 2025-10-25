---
title: "Building Blocks"
description: "Understand each block type used to compose flows."
---

## Blocks overview

<Frame>
  <img src="/images/blocks.png" alt="Descriptive alt text" />
</Frame>

- **Start**: flow entry; one source handle to begin execution
- **Master Agent**: core reasoning unit with prompt, tools, RAG, and variables
- **Child Agent**: reusable/embedded agent with its own variables and prompt
- **Tool**: external API/tool call node
- **Sub-Flow**: reference and invoke another flow (optional)
- **End**: terminal node for completion