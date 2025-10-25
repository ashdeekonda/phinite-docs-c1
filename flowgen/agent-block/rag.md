---
title: "RAG (Knowledge Base)"
description: "Attach data sources and collection items to ground agent responses."
---

## Attaching RAG

Use the RAG tab to select data sources and specific items (documents, tables, etc.). The selected list is saved with the agent and used at runtime.

<Steps>
  <Step title="Open RAG tab">
       <Frame>
  <img src="/Rag.png" alt="Descriptive alt text" />
</Frame>

    Select the agent block and open RAG.
  </Step>
  <Step title="Choose a data source">
    <Frame>
  <img src="/step-2.png" alt="Descriptive alt text" />
</Frame>
    
    Pick a source, then fetch and select items relevant to the agent’s task.
  </Step>
  <Step title="Save">
    <Frame>
  <img src="/step-3.png" alt="step-3" />
</Frame>
  
    Confirm to persist selections.
  </Step>
</Steps>

<Note>
  UI is implemented in `studio/components/drawer/RAG.tsx` and uses Redux slices for data sources and items.
</Note>