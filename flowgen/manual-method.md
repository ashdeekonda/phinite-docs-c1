---
title: "Manual Canvas Method"
description: "Design workflows by placing blocks on a visual canvas and connecting them with edges."
---

## Workflow creation on the canvas

<Steps>
  <Step title="Create a new flow">
    <Frame>
      ![New Flow](/images/new-flow.png)
    </Frame>

    Open Flowgen Studio and choose "Create manually".
  </Step>
  <Step title="Add blocks">
    <Frame>
      ![Add Blocks](/images/add-blocks.png)
    </Frame>

    Drag blocks from the Block Library: Start, Master Agent, Child Agent, Tool, End.
  </Step>
  <Step title="Connect with edges">
    <Frame>
      ![Connect With Edges](/images/connect-with-edges.png)
    </Frame>

    Connect source and target handles between blocks to define execution order.
  </Step>
  <Step title="Configure blocks">
    <Frame>
      ![Configure Blocks](/images/configure-blocks.png)
    </Frame>

    Select a block to edit its properties in the Inspector: prompts, RAG, tools, and variables.
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