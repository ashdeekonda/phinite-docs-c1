---
title: "Connections & Logic"
description: "Connect nodes with edges and use decision variables to branch logic."
---

## Connections overview

- **Handles**: drag from a source handle to a target handle to connect nodes
- **Edges**: represent execution order and data flow
- **Conditional logic**: use decision variables to route along labeled edges

## Handles (Source & Target)

- **Start**: source-only
- **End**: target-only
- **Agents/Tools**: source and target (varies by type)
- Drag from source to target to create a new edge

## Edges & Transitions

- **Create**: drag from a node's source handle to a target handle
- **Select**: click an edge to select; use keyboard shortcuts where available
- **Label**: set display labels and, optionally, conditions via the Inspector flow or edge label UI
- **Delete**: select and press Backspace/Delete

<Info>
Custom edge and label rendering is implemented in the studio components (e.g., `CustomEdge.tsx`, `CustomEdgeLabel.tsx`).
</Info>

## Conditional Edges (LLM Logic)

Agents can capture variables that summarize outcomes (e.g., status or category). You can reference these as decision variables to control which edge to traverse.

<Steps>
<Step title="Capture decision variables">
  In the agent's Variables tab, add Capture Variables the agent will produce (e.g., `status`).
</Step>
<Step title="Select decision variables">
  In the Decision tab, pick variables that drive branching.
</Step>
<Step title="Label edges">
  Label edges with descriptive outcomes (e.g., "approved", "needs_review").
</Step>
</Steps>

<Note>
Decision variable selection is configured in `drawer/Decision.tsx`. At runtime, your backend logic evaluates conditions to choose the edge.
</Note>
