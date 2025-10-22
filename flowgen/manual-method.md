---
title: "Manual Canvas Method"
description: "Design workflows by placing blocks on a visual canvas and connecting them with edges."
---

## Workflow creation on the canvas

<Steps>
  <Step title="Create a new flow">
    ![New Flow Pn](/MANUALAGENT.png)

    Open Flowgen Studio and choose "Create manually".
  </Step>
  <Step title="Add blocks">
    ![Manual Agent 1 Pn](/images/Manual-Agent-1.png)

    Drag blocks from the Block Library: Start, Master Agent, Child Agent, Tool, End.
  </Step>
  <Step title="Connect with edges">
    ![Manual Agent 2 Pn](/images/Manual-Agent-2.png)

    Connect source and target handles between blocks to define execution order.
  </Step>
  <Step title="Configure blocks">
    ![Manual Agent 3 Pn](/images/Manual-Agent-3.png)

    Select a block to edit its properties in the Inspector: prompts, RAG, tools, and variables.
  </Step>
  <Step title="Test and iterate">
    Run sample inputs, observe outputs, and refine prompts, variables, and edge conditions.
  </Step>
</Steps>

<Tip>
  Use variables to avoid re-computing values and to pass context across agents and tools.
</Tip>