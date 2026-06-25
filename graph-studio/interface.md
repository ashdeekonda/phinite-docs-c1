---
title: "Interface Layout"
description: "Learn the main areas of Graph Studio: Canvas, Node Library, Inspector, and Variables."
---

## Main areas

- **Canvas**: where you arrange and connect nodes
- **Node Library**: where you find available node types
- **Inspector Panel**: where you configure the selected node
- **Variables Panel**: where you manage inputs and captured values

## Canvas

The canvas is powered by React Flow (`src/components/flow/FlowCanvas.tsx`). It registers node types like `start`, `task`, `api`, `flow`, and `end`, and renders background, controls, and a minimap.

### Common actions

- **Pan/zoom**: mouse wheel or trackpad; controls are available in the bottom-right
- **Add nodes**: drag from the Node Library onto the canvas
- **Connect edges**: drag from a node's source handle to a target handle
- **Select/multi-select**: click nodes/edges; hold ⌘/Ctrl for multi-select
- **Delete**: select and press Backspace/Delete
- **Minimap**: toggle via settings to navigate large graphs

<Note>
Start/End nodes are non-deletable by default as defined in `src/utils/nodeUtils.ts`.
</Note>

## Node Library

### Available nodes

- **Start**: entry point for the Agent Graph
- **Master Agent (Task)**: primary agent with prompt, tools, RAG, and variables
- **Child Agent**: reusable/embedded agent node
- **Tool (API)**: calls external tools or APIs
- **Sub-Agent Graph (optional)**: reference another Agent Graph
- **End**: terminates the graph

<Info>
Node types correspond to React components in `src/components/nodes/` and are created with defaults via `createNode` in `src/utils/nodeUtils.ts`.
</Info>

### Adding nodes

- Drag nodes from the library onto the canvas.
- Place near existing nodes to keep edges readable.
- Use consistent naming in the Inspector to aid collaboration.

## Inspector Panel

The Inspector appears when you select a node. It's implemented as `NodeDrawer` in `studio/components/NodeDrawer.tsx`.

### Inspector tabs

- **Details**: name, description, and main prompt (`task_prompt`)
- **RAG**: attach data sources and items to ground the agent
- **Variables**: manage input variables and capture variables
- **Decision**: choose variables used for conditional edges
- **Agent Graph**: configure sub-flow parameters (for `flow` nodes)

<Tip>
Use the prompt refinement feature in Details to improve clarity and consistency before publishing.
</Tip>

## Variables Panel

Variables are configured in the Inspector's Variables tab:

- **Input Variables**: select from available values across the flow
- **Capture Variables**: define what the agent should extract or persist

<Note>
Child Agent variables are managed via `ChildVariables` to support nested/reusable agents.
</Note>
