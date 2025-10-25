---
title: "Variables (Input & Capture)"
description: "Define agent inputs and capture outputs for downstream logic."
---

## Variable types

- **Input Variables**: values provided to the agent from earlier steps or user input
- **Capture Variables**: values the agent extracts/produces for downstream use

<Steps>
  <Step title="Select inputs">
    <Frame>
  <img src="/images/input-var.png" alt="step-1
  " />
</Frame>

    In Variables, pick inputs from available flow variables.
  </Step>
  <Step title="Add captures">
   <Frame>
  <img src="/images/final.png" alt="step-1
  " />
</Frame>
  
    Add capture variables to persist outputs (e.g., `summary`, `status`, `email`).
  </Step>
  <Step title="Use in decisions">
    <Frame>
  <img src="/images/variables.png" alt="step-1
  " />
</Frame>
    
    Reference captured variables in the Decision tab to drive conditional edges.
  </Step>
</Steps>