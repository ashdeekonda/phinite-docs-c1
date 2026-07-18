---
title: Canvas
description: The Graph Studio canvas — pan, zoom, select nodes, and connect edges.
---

The **canvas** is the main React Flow surface where you place [nodes](/graph-studio/nodes) and [connections](/graph-studio/connections).

## What you can do

| Action | How |
| --- | --- |
| **Pan** | Drag the canvas background |
| **Zoom** | Scroll or use zoom controls |
| **Select a node** | Click a node — opens the [Inspector](/graph-studio/interface/inspector-panel) drawer |
| **Connect nodes** | Drag from a source handle to a target handle |
| **Multi-select** | Shift-click or marquee select (when enabled) |

## Workflow on the canvas

1. Add nodes from the toolbar or [Node Library](/graph-studio/interface/node-library).
2. Connect **Start** → agents → **Tool** nodes (as needed) → **End**.
3. Click each agent node and complete drawer tabs before **Save**.
4. Use **Test** from the toolbar to validate runs without deploying.

<Note>
  When the node drawer opens, the canvas may pan to keep the selected node visible. Closing the drawer restores the prior viewport.
</Note>

## Related

- [Interface layout](/graph-studio/interface)
- [Handles & edges](/graph-studio/connections/handles)
- [Manual canvas method](/graph-studio/manual-method)
