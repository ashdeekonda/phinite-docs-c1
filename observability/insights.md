---
title: Observability Insights
description: Default Observability landing — KPIs, trends, agent health, Cost (Phinite), drill to Sessions.
---

**Insights** is the default tab on **OPERATE → Observability** (`?tab=insights`). It summarizes session health and cost, then drills into **Sessions**.

No Pro plan gate on Insights (permission: `workspace.reports.read` / sidebar `workspace.sidebar.reports`). Insights APIs need ClickHouse configured (otherwise the backend may return `503`).

<Frame caption="Observability Insights">
  <img src="/images/v2/observability/01-insights.png" alt="Insights KPIs and session trend" />
</Frame>

## Ranges and filters

| Control | Values |
| --- | --- |
| Range | **Last 24 hours** · **Last 7 days** · **Last 30 days** · **Last 90 days** (+ custom where offered) |
| Filters | Channel · Source · Env · Scope · Agent / flow (`i_*` URL state) |
| Actions | **Refresh** |

## KPI tiles

| Title | Meaning |
| --- | --- |
| **Sessions in range** | Count for filters / window (workspace total in subtitle) |
| **Success rate** | Successful sessions share |
| **Total failures/errors** | Error volume impacting sessions |
| **Policy blocks** | Governance denials affecting sessions |
| **Total tokens** | Input · Output breakdown |
| **Cost (Phinite)** | Billable platform usage for the range |
| **Open incidents** | Grouped by agent + failure type |
| **Active alerts** | Recent failure signals by session |

## Sections below the KPIs

| Section | Contents |
| --- | --- |
| **Session & failure trend** | Legend **Sessions** · **Failed sessions** (hourly/daily) |
| **Agent health** | Columns **Agent** · **Health** · **Sessions** · **Success** · **P95** · **Cost / session** · **Alerts** |
| **Open incidents** / **Active alerts** | Operational lists |
| **Failures & errors** | **Sessions with failures** · **Runtime errors** · **Tool failures** · **HTTP errors** · **By failure type** |
| Breakdowns | **Model calls distribution** · **By channel** · **By source** · **By environment** (click → Sessions filters) |

## Drill to Sessions

1. Stay on Insights or click a breakdown / KPI that supports drill-down.
2. Switch to **Sessions** (`?tab=sessions`) — filters map via `s_*` URL state.
3. Open a row → session detail or **Investigate**.

<Frame caption="Observability Sessions">
  <img src="/images/v2/observability/02-sessions.png" alt="Sessions table" />
</Frame>

### Sessions columns

**Date / Time** · **Session ID** · **Graph name** · **Channel** · **Session Status** · **Env** · **Source** · **Turns** · **Duration** · **Cost** · **Eval score** · **Scope**

Export zip is available from the Sessions UI where enabled.

## APIs

`GET /observability/insights/{summary,trend,breakdowns,agent-health,failures,operational,recent}`

## Related

- [Investigate](/observability/investigate)
- [Observability overview](/observability/overview)
- [Session logs](/observability/logs)
- [Governance](/governance/overview)
- [Evaluations](/evaluations/overview)
