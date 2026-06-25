---
title: "Methods of workflow creation"
description: "Create agent graphs with Aura (prompt-based) or by building manually on the canvas."
---

Graph Studio supports two ways to create agent graphs. Pick Aura for fast drafts; use the manual canvas for full control.

## Aura method

Aura translates a plain-language prompt into a draft canvas with nodes, edges, tools, and variable suggestions. You can accept, refine, or extend the proposal on the canvas.

<Steps>
  <Step title="Open Graph Studio">
    Go to the Graph Studio page in your project.
  </Step>
  <Step title="Start a new agent graph with Aura">
    Choose **Create with Aura** and describe your objective, inputs, data sources, tools, and expected outputs.

    <Tip>
      Specify relevant collections and tools to improve grounding and structure.
    </Tip>
  </Step>
  <Step title="Review the draft">
    Aura generates Start, Agent, Tool, and End nodes, connects edges, and proposes variables.

    Validate assumptions and refine prompts, RAG settings, tools, and variables.
  </Step>
  <Step title="Refine and save">
    Edit agent prompts, attach collections, wire variables, and save the graph.

    <Check>
      You should see a coherent path from Start to End with any branches clearly labeled.
    </Check>
  </Step>
</Steps>

### Prompt tips

- **Goal**: what the agent graph should achieve and for whom
- **Inputs**: list input variables and formats
- **Knowledge**: name relevant collections or domains
- **Tools**: APIs or actions to call
- **Success criteria**: expected outputs or acceptance checks

## Manual method

Design agent graphs by placing nodes on the visual canvas and connecting them with edges.

<Steps>
  <Step title="Create a new agent graph">
    <Frame>
      ![New Agent Graph](/images/new-flow.png)
    </Frame>

    Open Graph Studio and choose **Create manually**.
  </Step>
  <Step title="Add nodes">
    <Frame>
      ![Add Blocks](/images/add-blocks.png)
    </Frame>

    Drag nodes from the Node Library: Start, Master Agent, Child Agent, Tool, End.
  </Step>
  <Step title="Connect with edges">
    <Frame>
      ![Connect With Edges](/images/connect-with-edges.png)
    </Frame>

    Connect source and target handles between nodes to define execution order.
  </Step>
  <Step title="Configure nodes">
    <Frame>
      ![Configure Blocks](/images/configure-blocks.png)
    </Frame>

    Select a node to edit its properties in the Inspector: prompts, RAG, tools, and variables.
  </Step>
  <Step title="Test and iterate">
    <Frame>
      ![Test And Iterate](/images/test-and-iterate.png)
    </Frame>

    Run sample inputs, observe outputs, and refine prompts, variables, and edge conditions.
  </Step>
</Steps>

<Tip>
  Use variables to avoid re-computing values and to pass context across agents and tools.
</Tip>
