---
title: Observability Insights
description: Default Observability landing — session health, Cost (Phinite), and drill to Sessions.
---

**Insights** is the default landing tab for **OPERATE → Observability**. It summarizes session volume, success, failures, policy blocks, tokens, and **Cost (Phinite)** for the selected range, then lets you drill into **Sessions**.

<Frame caption="Observability Insights — KPIs and session trend">
  <img src="/images/v2/observability/01-insights.png" alt="Observability Insights dashboard with Cost Phinite and session trend" />
</Frame>

## What Insights shows

| Signal | Meaning |
| --- | --- |
| **Sessions in range** | Count for the selected filters / time window |
| **Success rate** | Share of successful sessions |
| **Total failures/errors** | Error volume impacting sessions |
| **Policy blocks** | Sessions affected by governance denials |
| **Total tokens** | Input / output token totals |
| **Cost (Phinite)** | Billable platform usage for the range |
| **Open incidents** | Grouped failure themes |
| **Active alerts** | Recent failure signals |

Filters commonly include channel, source, env, scope, agent graph, and time range (**Last 7 days**, custom, refresh).

## Drill to Sessions

1. Open **Observability** (Insights loads by default).
2. Apply filters or click a chart / KPI that supports drill-down.
3. Switch to **Sessions** (or follow the drilled filter) to inspect individual runs.

<Frame caption="Observability Sessions">
  <img src="/images/v2/observability/02-sessions.png" alt="Observability Sessions tab" />
</Frame>

From a session, continue into [timeline](/observability/logs/timeline), [decision joints](/observability/logs/decision-joints), and [variables](/observability/logs/variables) as needed.

## Related

- [Observability overview](/observability/overview)
- [Usage metrics](/observability/usage-metrics)
- [Billing](/observability/billing)
- [Governance](/governance/overview)
