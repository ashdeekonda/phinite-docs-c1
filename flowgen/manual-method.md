---
title: "Manual Canvas Method"
description: "Design workflows by placing blocks on a visual canvas and connecting them with edges."
---

## Workflow creation on the canvas

<Steps>
  <Step title="Create a new flow">
    <img
      src="/Create-a-new-flow.png"
      alt="New Flow Pn"
      title="New Flow Pn"
      style={{ width:"73%" }}
    />

    Open Flowgen Studio and choose "Create manually".
  </Step>
  <Step title="Add blocks">
    <img
      src="/Manual-Agent-1.png"
      alt="Manual Agent 1 Pn"
      title="Manual Agent 1 Pn"
      style={{ width:"72%" }}
    />

    Drag blocks from the Block Library: Start, Master Agent, Child Agent, Tool, End.
  </Step>
  <Step title="Connect with edges">
    <img
      src="/Manual-Agent-2.png"
      alt="Manual Agent 2 Pn"
      title="Manual Agent 2 Pn"
      style={{ width:"73%" }}
    />

    Connect source and target handles between blocks to define execution order.
  </Step>
  <Step title="Configure blocks">
    <img
      src="/Manual-Agent-3.png"
      alt="Manual Agent 3 Pn"
      title="Manual Agent 3 Pn"
      style={{ width:"73%" }}
    />

    Select a block to edit its properties in the Inspector: prompts, RAG, tools, and variables.
  </Step>
  <Step title="Test and iterate">
    <img
      src="/test-agent1.png"
      alt="Test Agent Pn"
      style={{ width:"74%" }}
      title=""
    />

    Run sample inputs, observe outputs, and refine prompts, variables, and edge conditions.
  </Step>
</Steps>

<Tip>
  Use variables to avoid re-computing values and to pass context across agents and tools.
</Tip>