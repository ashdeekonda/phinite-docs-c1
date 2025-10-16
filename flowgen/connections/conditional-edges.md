---
title: "Conditional Edges (LLM Logic)"
description: "Use decision variables to route execution along different paths."
---

## Concept

Agents can capture variables that summarize outcomes (e.g., status or category). You can reference these as decision variables to control which edge to traverse.

<Steps>
<Step title="Capture decision variables">
  In the agent’s Variables tab, add Capture Variables the agent will produce (e.g., `status`).
</Step>
<Step title="Select decision variables">
  In the Decision tab, pick variables that drive branching.
</Step>
<Step title="Label edges">
  Label edges with descriptive outcomes (e.g., “approved”, “needs_review”).
</Step>
</Steps>

<Note>
Decision variable selection is configured in `drawer/Decision.tsx`. At runtime, your backend logic evaluates conditions to choose the edge.
</Note>
