---
title: Tools integration
description: Attach published tools to Master and Child Agent nodes in the drawer Tools tab.
---

The **Tools** tab lets an agent call workspace **published tools** — custom tools from [Tools & Dev Studio](/devstudio/overview) and predefined integrations.

## Attach tools

1. Select a **Master Agent** or **Child Agent** node.
2. Open the drawer → **Tools** tab.
3. Click to connect a tool — the **Connect Tool** dialog lists published tools.
4. Map tool inputs from [variables](/graph-studio/agent-node/variables) where required.
5. For predefined tools, enable individual **sub-tools** as needed.
6. **Save** the graph.

<Frame caption="Graph-scoped Tools panel in Studio sidebar">
  <img src="/images/v2/studio/02-tools-sidebar.png" alt="Studio Tools sidebar" />
</Frame>

<Note>
  Tools must be published before **Build**. Unpublished tools show **Publish** in the build dialog.
</Note>

## Graph vs workspace tools

| Surface | Scope |
| --- | --- |
| Studio → **Tools** (sidebar) | Tools linked to this Agent Graph |
| Workspace → **Tools** (`/all-tools`) | Create and publish tools; **Open Dev Studio** |

## Related

- [Tool node](/graph-studio/nodes/tool-node)
- [Tools & Dev Studio](/devstudio/overview)
- [Builds](/builds/overview)
