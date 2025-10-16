---
title: "Block Library"
description: "Add Start, Agent, Child Agent, Tool, and End blocks to the canvas."
---

## Available blocks

- **Start**: entry point for the flow
- **Master Agent (Task)**: primary agent with prompt, tools, RAG, and variables
- **Child Agent**: reusable/embedded agent block
- **Tool (API)**: calls external tools or APIs
- **Sub-Flow (optional)**: reference another flow
- **End**: terminates the flow

<Info>
Blocks correspond to React components in `src/components/nodes/` and are created with defaults via `createNode` in `src/utils/nodeUtils.ts`.
</Info>

## Adding blocks

- Drag blocks from the library onto the canvas.
- Place near existing nodes to keep edges readable.
- Use consistent naming in the Inspector to aid collaboration.
