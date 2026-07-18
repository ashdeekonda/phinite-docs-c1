---
title: Tools
description: Build and manage tools used by agent graphs.
---

Tools are callable integrations or custom functions. Attach them to nodes in Graph Studio; manage the library from workspace **Tools**.

## Where

| Place | Use |
| --- | --- |
| Workspace **Tools** | Tool list — create, version, archive |
| **Open Dev Studio** | Code editor for a tool |
| Studio → **Tools** | Tools scoped to the open agent graph |
| Studio → **Integrations** → Integration Tools | Connect app integrations |
| Build / Expose wizards | Pin tool versions; [export to build](/configure/build-export) |

![Workspace Tools](/images/v2/devstudio/01-all-tools.png)

## Steps

1. Open **Tools** in the workspace sidebar.
2. Click **New Tool**, or select a row and **Open Dev Studio**.
3. Implement and **Publish** a version.
4. In Graph Studio, attach the published tool to a [Tool node](/studio/nodes) or agent **Tools** tab.
5. **Save** the graph.
6. On **Build**, confirm tool versions (unpublished tools show **Publish**).

## Integration tools vs custom tools

- **Custom tools** — authored in Dev Studio from workspace **Tools**.
- **Integration Tools** — prebuilt app connectors configured under [Integrations](/configure/integrations).

## Related

- [Build an agent graph](/agents/build-graph)
- [Node types](/studio/nodes)
- [Builds](/agents/builds)
- [Build export](/configure/build-export)
