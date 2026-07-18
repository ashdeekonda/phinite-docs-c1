---
title: Variables
description: Flow variables, session variables, input and capture on agent nodes.
---

## What this is

**Variables** carry state through an Agent Graph run: user inputs, extracted values, and values passed between nodes. Phinite distinguishes:

- **Flow / graph variables** — schemas and defaults for the whole graph (Studio variables panel).
- **Node variables** — **Input** (read from flow/session) and **Capture** (write extracted values) on each agent node.

## Where in the product

| Surface | Path |
| --- | --- |
| Graph variables | Studio → open graph → variables panel (`?tab=variables` when enabled) |
| Node drawer | Select node → **Variables** tab |
| Child agents | **Child Variables** tab on Child Agent nodes |

![Variables panel](/images/v2/studio/03-variables.png)

## Steps — graph variables

1. Open **Graph Studio** for your Agent Graph.
2. Open the **Variables** panel for the graph (when available in your Studio layout).
3. Define variable names, types, and defaults as required by your graph design.
4. **Save**.

## Steps — node input and capture

1. Select a **Master Agent** or **Child Agent** node.
2. Open the **Variables** tab in the node drawer.
3. Under **Input Variables**, map values available from the flow or session.
4. Under **Capture Variables**, define fields the model should extract and persist.
5. **Save** the graph.

## Builds and deploy

Captured variables can be referenced by tools and downstream nodes. Env-specific secrets belong in [Env. variables](/configure/env-variables), not in graph variable definitions.

## Related

- [Node types](/studio/nodes)
- [Configuration overview](/configure/overview)
- [Build export](/configure/build-export)
