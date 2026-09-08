---
title: Evaluations overview
description: Workspace Analytics and History / Sessions for agent evaluation runs.
icon: chart-mixed
---

**Evaluations** measure how Agent Graphs score against metrics across builds and drafts. Use the workspace **OPERATE → Evaluations** page for fleet Analytics and History; configure runs from Graph Studio ([Studio evaluations](/evaluations/studio)).

<Note>
  Evaluations require a **Pro+** plan. Locked Studio sidebar items still show the Evaluations entry with an upgrade hint when the plan does not include the feature.
</Note>

<Frame caption="Evaluations — Analytics tab">
  <img src="/images/v2/evals/01-analytics.png" alt="Evaluations Analytics with KPIs and volume heatmap" />
</Frame>

## Workspace tabs

| Tab | What you see |
| --- | --- |
| **Analytics** | Runs in range, completed, pass rate, failed runs; volume heatmap; breakdowns by dataset, environment, mode, flow; recent runs |
| **History / Sessions** | Paginated run list and run detail for deeper review |

Filters typically include a date range (for example **Last 7 days**) and **Refresh**.

<Frame caption="Evaluations — History / Sessions">
  <img src="/images/v2/evals/02-history.png" alt="Evaluations History / Sessions tab" />
</Frame>

## Datasets and modes

Evaluation wizards use **datasets** (Simulation, Autonomous, or Production) and **modes** (Agentic, Single-turn, or Multi-turn), then attach **metrics** and review. Production datasets can pull from observability sessions.

<Note>
  Running evaluations against **Production** is limited to **Superadmin** and **QA**. Admins and Developers use **Development** and **UAT**.
</Note>

## How runs get created

From Graph Studio’s **Agent Evaluations** panel you can:

- **Connect to Build** — attach metrics to a build for live or scheduled scoring
- **Run on draft** — evaluate the current flow version with mixed metrics
- **Experiment** — compare builds or build vs draft
- **Signal** — toggle signal ingest on a build

See [Studio evaluations](/evaluations/studio) for the panel walkthrough. Run history and analytics always land back on this workspace page.

## Related

<CardGroup cols={2}>
  <Card title="Studio evaluations" icon="flask" href="/evaluations/studio">
    Connect to Build, Run on draft, Experiment, Signal.
  </Card>
  <Card title="Governance" icon="shield" href="/governance/overview">
    Tool and LLM controls that affect production behavior.
  </Card>
  <Card title="Observability" icon="chart-line" href="/observability/overview">
    Insights and sessions for live traffic.
  </Card>
  <Card title="Builds" icon="box" href="/builds/overview">
    Pin graph versions that evaluations score.
  </Card>
</CardGroup>
