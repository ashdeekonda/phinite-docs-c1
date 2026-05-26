---
title: "Node Library"
description: "Add Start, Agent, Child Agent, Tool, and End nodes to the canvas."
---

## Available nodes

- **Start**: entry point for the Agent Graph
- **Master Agent (Task)**: primary agent with prompt, tools, RAG, and variables
- **Child Agent**: reusable/embedded agent node
- **Tool (API)**: calls external tools or APIs
- **Sub-Agent Graph (optional)**: reference another Agent Graph
- **End**: terminates the graph

<Info>
Node types correspond to React components in `src/components/nodes/` and are created with defaults via `createNode` in `src/utils/nodeUtils.ts`.
</Info>

## Adding nodes

- Drag nodes from the library onto the canvas.
- Place near existing nodes to keep edges readable.
- Use consistent naming in the Inspector to aid collaboration.
