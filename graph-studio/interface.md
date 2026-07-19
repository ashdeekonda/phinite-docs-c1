---
title: Interface layout
description: Canvas, node library, node drawer (Inspector), and variables panel in Graph Studio.
---

Graph Studio splits design work across four main areas. Together they cover layout, node palette, per-node configuration, and graph-level variables.

<CardGroup cols={2}>
  <Card title="Canvas" icon="layout" href="/graph-studio/interface/canvas">
    Arrange and connect nodes; pan and zoom the graph.
  </Card>
  <Card title="Node types" icon="grid" href="/graph-studio/nodes">
    Add Start, Master Agent, Child Agent, Tool, and End from the canvas toolbar.
  </Card>
  <Card title="Inspector (node drawer)" icon="sliders" href="/graph-studio/interface/inspector-panel">
    Configure prompt, RAG, tools, and variables for the selected node.
  </Card>
  <Card title="Variables panel" icon="database" href="/graph-studio/interface/variables-panel">
    Define flow and session variables for the whole graph.
  </Card>
</CardGroup>

## Toolbar (top of canvas)

| Control | Action |
| --- | --- |
| **Save** | Persist the current graph draft |
| **Build** | Open the build dialog — pins graph + tool versions (requires Save) |
| **Deploy** | Open deploy dialog — requires at least one build |
| **Test** | Open test drawer (chat / voice / autonomous depending on graph type) |

<Frame caption="Graph Studio toolbar — Save, Build, Deploy, Test">
  <img src="/images/v2/studio/01-studio-aura-shell.png" alt="Graph Studio toolbar" />
</Frame>

## Left sidebar

Under **Graph assets** for the open graph:

- **Graph Versions**, **Agent Builds**, **Agent Cards**, **Triggers**, **Integrations**, **Tools**

See [Graph Studio overview](/graph-studio/overview#graph-assets-sidebar).

## Related

- [Graph Studio overview](/graph-studio/overview)
- [Node types](/graph-studio/nodes)
