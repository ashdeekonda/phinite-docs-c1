---
title: Observability overview
description: Insights and Sessions for Agent Graph runs.
---

**Observability** shows how Agent Graphs behave in production. Open **OPERATE → Observability**. The hub has two tabs: **Insights** (default) and **Sessions**.

Permission: `workspace.reports.read` (sidebar `workspace.sidebar.reports`). Not Pro-gated.

<CardGroup cols={2}>
  <Card title="Insights" href="/observability/insights">
    KPIs, Cost (Phinite), trends — then drill to Sessions.
  </Card>
  <Card title="Governance" href="/governance/overview">
    Policy blocks on Insights come from tool policies.
  </Card>
  <Card title="Evaluations" href="/evaluations/overview">
    Score quality separately from runtime telemetry.
  </Card>
  <Card title="Guardrails" href="/guardrails/overview">
    LLM safety profiles that shape session outcomes.
  </Card>
</CardGroup>

## Tabs

| Tab | `?tab=` | Purpose |
| --- | --- | --- |
| **Insights** | `insights` (default) | Fleet KPIs and charts for the selected range |
| **Sessions** | `sessions` | Filterable session list — open a row for classic session logs |

Route: `/{org}/workspace/{workspaceId}/observability`

<Frame caption="Observability — Insights">
  <img src="/images/v2/observability/01-insights.png" alt="Observability Insights" />
</Frame>

See [Insights & Sessions](/observability/insights) for KPI definitions, filters, and the Sessions table.

## Related

- [Insights & Sessions](/observability/insights)
- [Governance](/governance/overview)
- [Evaluations](/evaluations/overview)
