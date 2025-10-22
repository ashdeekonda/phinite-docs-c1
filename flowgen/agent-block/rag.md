---
title: "RAG (Knowledge Base)"
description: "Attach data sources and collection items to ground agent responses."
---

## Attaching RAG

Use the RAG tab to select data sources and specific items (documents, tables, etc.). The selected list is saved with the agent and used at runtime.

<Steps>
  <Step title="Open RAG tab">
    Select the agent block and open RAG.
  </Step>
  <Step title="Choose a data source">
    Pick a source, then fetch and select items relevant to the agent’s task.
  </Step>
  <Step title="Save">
    Confirm to persist selections.
  </Step>
</Steps>

<Note>
  UI is implemented in `studio/components/drawer/RAG.tsx` and uses Redux slices for data sources and items.
</Note>