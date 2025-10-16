---
title: "Canvas"
description: "Use the canvas to place nodes, connect edges, and control layout."
---

## Canvas basics

The canvas is powered by React Flow (`src/components/flow/FlowCanvas.tsx`). It registers node types like `start`, `task`, `api`, `flow`, and `end`, and renders background, controls, and a minimap.

### Common actions

- **Pan/zoom**: mouse wheel or trackpad; controls are available in the bottom-right
- **Add blocks**: drag from the Block Library onto the canvas
- **Connect edges**: drag from a node’s source handle to a target handle
- **Select/multi-select**: click nodes/edges; hold ⌘/Ctrl for multi-select
- **Delete**: select and press Backspace/Delete
- **Minimap**: toggle via settings to navigate large flows

<Note>
Start/End blocks are non-deletable by default as defined in `src/utils/nodeUtils.ts`.
</Note>
