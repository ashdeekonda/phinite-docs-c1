---
title: "Aura Method (Prompt-Based)"
description: "Bootstrap a new workflow by describing your goal in natural language."
---

## How it works

Aura translates a plain-language prompt into a draft canvas with nodes, edges, tools and variable suggestions. You can accept, refine, or extend the proposal on the canvas.

<Steps>
  <Step title="Open Graph Studio">
    Go to the Graph Studio page in your project.
  </Step>
  <Step title="Start a new Agent Graph with Aura">
    Choose "Create with Aura" and describe your objective, inputs, data sources, tools, and expected outputs.

    <Tip>
      Specify relevant collections and tools to improve grounding and structure.
    </Tip>
  </Step>
  <Step title="Review the draft">
    Phinite Aura generates Start, Agent, Tool, and End nodes, connects edges, and proposes variables.

    Validate assumptions and refine prompts, RAG settings, tools, and variables.
  </Step>
  <Step title="Refine and save">
    Edit agent prompts, attach collections, wire variables, and save the graph.

    <Check>
      You should see a coherent path from Start to End with any branches clearly labeled.
    </Check>
  </Step>
</Steps>

## Prompt Tips

- **Goal**: what the Agent Graph should achieve and for whom
- **Inputs**: list input variables and formats
- **Knowledge**: name relevant collections or domains
- **Tools**: APIs or actions to call
- **Success criteria**: expected outputs or acceptance checks

<Tip>
  Use variables to avoid re-computing values and to pass context across agents and tools.
</Tip>