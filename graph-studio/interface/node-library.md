---
title: Node Library
description: Add Start, Master Agent, Child Agent, Tool, and End nodes to the canvas.
---

The **Node Library** (canvas toolbar / add-node menu) lists node types you can place on the [canvas](/graph-studio/interface/canvas).

## Available node types

| Node | Use when |
| --- | --- |
| **Start** | Every graph needs one entry node |
| **Master Agent** | Primary reasoning step with full drawer tabs |
| **Child Agent** | Delegated sub-task with its own prompt and tools |
| **Tool** | Direct integration call without LLM orchestration |
| **End** | Run completes |

See [Node types](/graph-studio/nodes) for roles and links to per-type pages.

## Add a node

1. Open the add-node control on the canvas toolbar.
2. Choose a node type.
3. Click on the canvas to place it (or drag from the palette if your layout supports drag).
4. Connect handles to existing nodes ([Connections](/graph-studio/connections)).

<Tip>
  Start with **Start** → **Master Agent** → **End** for a minimal graph, then add **Tool** and **Child Agent** nodes as needed.
</Tip>

## Registry agents

Registry agents are attached from a **Master Agent** drawer (Browse / Discovery), not as a separate library tile. See [Registry agent nodes](/agent-registry/registry-agent-nodes).

## Related

- [Node types](/graph-studio/nodes)
- [Master Agent node](/graph-studio/nodes/master-node)
