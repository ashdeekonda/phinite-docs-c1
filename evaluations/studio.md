---
title: Studio evaluations
description: Connect metrics to builds, run on draft, experiment, and toggle signal from Graph Studio.
---

Open **Evaluations** in the Graph Studio sidebar to configure how this Agent Graph is scored. The panel title is **Agent Evaluations**; a **History** link jumps to the workspace Evaluations page.

<Frame caption="Agent Evaluations — choose how to evaluate this agent">
  <img src="/images/v2/evals/03-studio-panel.png" alt="Studio Agent Evaluations with Connect to Build, Run on draft, Experiment, Signal" />
</Frame>

## Options

| Action | Description |
| --- | --- |
| **Connect to Build** | Attach metrics to a build for live or scheduled scoring |
| **Run on draft** | Evaluate the current flow version with mixed metrics |
| **Experiment** | Compare builds or build vs draft |
| **Signal** | Toggle signal ingest on a build |

The panel states that run history and analytics live on the workspace **Evaluations** page.

## Typical path

1. Open the Agent Graph in Graph Studio.
2. Click **Evaluations** in the Studio sidebar (`?tab=eval`).
3. Choose **Connect to Build**, **Run on draft**, **Experiment**, or **Signal**.
4. Complete the follow-up form for metrics, builds, or signal toggles.
5. Review results under **OPERATE → Evaluations** ([overview](/evaluations/overview)).

<Tip>
  Prefer **Connect to Build** when you want ongoing scores on a pinned build; use **Run on draft** while iterating before the next Build.
</Tip>

## Related

- [Evaluations overview](/evaluations/overview)
- [Builds overview](/builds/overview)
- [Graph Studio overview](/graph-studio/overview)
