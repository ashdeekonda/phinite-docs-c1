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
      ![Select Inputs](/images/select-inputs.png)
    </Frame>

    In Variables, pick inputs from available flow variables.
  </Step>
  <Step title="Add captures">
    <Frame>
      ![Add Captures](/images/add-captures.png)
    </Frame>

    Add capture variables to persist outputs (e.g., `summary`, `status`, `email`).
  </Step>
  <Step title="Use in decisions">
    <Frame>
      ![Use Decisions](/images/use-decisions.png)
    </Frame>

    Reference captured variables in the Decision tab to drive conditional edges.
  </Step>
</Steps>