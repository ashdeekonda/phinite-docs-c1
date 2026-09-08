---
title: Evaluations overview
description: Workspace Analytics and History / Sessions for agent evaluation runs (Pro+).
icon: chart-mixed
---

**Evaluations** score Agent Graphs against metrics across builds and drafts. Workspace **OPERATE → Evaluations** shows fleet **Analytics** and **History / Sessions**. Configure runs from Graph Studio **Agent Evaluations**.

<Note>
  Requires **Professional** or **Enterprise**. UI: `evaluationsIncluded` / upgrade wall. API: `MinPlan.Evaluations` on `/eval/*`. Permissions: `workspace.evaluations.{read,configure,run,delete_run}`.
</Note>

<CardGroup cols={2}>
  <Card title="Studio panel" icon="flask" href="/evaluations/studio">
    Connect to Build, Run on draft, Experiment, Signal.
  </Card>
  <Card title="Connect to Build" icon="link" href="/evaluations/connect-to-build">
    Live or scheduled scoring on a build.
  </Card>
  <Card title="Run on draft" icon="play" href="/evaluations/run-on-draft">
    Simulation, Autonomous, and Production datasets.
  </Card>
  <Card title="Observability" icon="chart-line" href="/observability/insights">
    Production sessions that can feed eval datasets.
  </Card>
</CardGroup>

## Where in the product

| Surface | Path |
| --- | --- |
| Workspace | `/{org}/workspace/{workspaceId}/evaluations` |
| Analytics | default or `?tab=analytics` |
| History | `?tab=history` — label **History / Sessions** |
| Studio | Graph Studio rail **Evaluations** → `?tab=eval` |

<Frame caption="Evaluations — Analytics">
  <img src="/images/v2/evals/01-analytics.png" alt="Evaluations Analytics KPIs" />
</Frame>

## Analytics

Range: **Last 7 days** / **Last 30 days** / **Last 90 days** · **Refresh**.

| KPI | Meaning |
| --- | --- |
| **Runs in range** | Evaluation runs in the selected window (also shows workspace total) |
| **Completed** | Finished runs · failed · success % |
| **Pass rate** | Metric / session units passed |
| **Failed runs** | Status = failed |

Breakdowns: **By dataset** · **By environment** · **By mode** · **By flow** · volume heatmap · **Recent runs** → **View history**.

## History / Sessions

<Frame caption="Evaluations — History / Sessions">
  <img src="/images/v2/evals/02-history.png" alt="History Sessions tab" />
</Frame>

| Filter | Examples |
| --- | --- |
| Search | `Run ID, session ID…` |
| **Flow** | Agent Graph |
| Version | Build / flow version |
| **Env** | Development / UAT / Production |
| **Status** | Completed / Failed / Running |

Columns: **Dataset** · **Status** · **Mode** · **Version** · **Env** · **Result** · **When** · **Run** (delete if `workspace.evaluations.delete_run`).

Open a run for the detail drawer (metrics, cases, logs).

## Datasets and modes

| Dataset | Typical use |
| --- | --- |
| **Simulation** | Scripted conversational scenarios |
| **Autonomous** | Message / variable / outcome cases |
| **Production** | Sessions from observability |

| Mode | UI label |
| --- | --- |
| Agentic | **Agentic eval** |
| Single-turn | **Single-turn eval** |
| Multi-turn | **Multi-turn eval** |

Environments: **Development** · **UAT** · **Production**.

<Note>
  Running against **Production** is limited to **Superadmin** and **QA**. Admins and Developers use **Development** and **UAT**.
</Note>

## APIs (summary)

Prefix `/eval` (Pro+): `/analytics`, `/runs`, `/metrics`, `/config`, `/dataset/*`, `/run`, `/run-mixed-metrics`, `/run-production-sessions`, `/evaluations`, `/evaluations/connect-to-build`, streams, scenario generators.

## Related

- [Studio evaluations](/evaluations/studio)
- [Connect to Build](/evaluations/connect-to-build)
- [Run on draft](/evaluations/run-on-draft)
- [Governance](/governance/overview)
