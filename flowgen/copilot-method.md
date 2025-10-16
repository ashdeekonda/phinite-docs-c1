---
title: "Copilot Method (Prompt-Based)"
description: "Bootstrap a new workflow by describing your goal in natural language."
---

## How it works

Copilot translates a plain-language prompt into a draft canvas with blocks, edges, and variable suggestions. You can accept, refine, or extend the proposal on the canvas.

<Steps>
<Step title="Open Flowgen Studio">
  Go to the Flowgen Studio page in your project.
</Step>

<Step title="Start a new flow with Copilot">
  Choose "Create with Copilot" and describe your objective, inputs, data sources, tools, and expected outputs.
  <Tip>Specify relevant collections and tools to improve grounding and structure.</Tip>
</Step>

<Step title="Review the draft">
  Copilot generates Start/Agent/Tool/End blocks, connects edges, and proposes variables. Validate assumptions and adjust prompts, RAG, tools, and variables.
</Step>

<Step title="Refine and save">
  Edit agent prompts, attach collections, wire variables, and save the flow.
  <Check>You should see a coherent path from Start to End with any branches clearly labeled.</Check>
</Step>
</Steps>

## Prompt tips

- **Goal**: what the flow should achieve and for whom
- **Inputs**: list input variables and formats
- **Knowledge**: name relevant collections or domains
- **Tools**: APIs or actions to call
- **Success criteria**: expected outputs or acceptance checks


