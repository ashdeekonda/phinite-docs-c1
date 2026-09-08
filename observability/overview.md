---
title: Observability overview
description: Insights, Sessions, Investigate, metrics, and logs for Agent Graph runs.
---

Observability shows how **Agent Graphs** behave in each environment. Open **OPERATE → Observability**. Default landing is **[Insights](/observability/insights)**; dig into **Sessions**, **[Investigate](/observability/investigate)**, classic logs, and billing allocation.

<CardGroup cols={2}>
  <Card title="Insights" href="/observability/insights">
    KPIs, Cost (Phinite), agent health, drill to Sessions.
  </Card>
  <Card title="Investigate" href="/observability/investigate">
    Span / Timeline / Conversation studio per session.
  </Card>
  <Card title="Usage metrics" href="/observability/usage-metrics">
    Sessions, tokens, and telephony KPIs.
  </Card>
  <Card title="Session logs" href="/observability/logs">
    Timeline, decisions, and captured variables.
  </Card>
  <Card title="Filtering" href="/observability/filtering">
    Slice by graph, environment, channel, and time.
  </Card>
  <Card title="Billing" type="note" href="/observability/billing">
    Cost breakdowns tied to runtime usage.
  </Card>
</CardGroup>

## Product map

| Surface | Route / tab |
| --- | --- |
| Hub | `…/observability` |
| **Insights** (default) | `?tab=insights` |
| **Sessions** | `?tab=sessions` |
| Session detail | `…/observability/{sessionId}` |
| **Investigate** | `…/observability/{sessionId}/investigate` |

Permission: `workspace.reports.read` (sidebar `workspace.sidebar.reports`). Insights is **not** Pro-gated (unlike Governance / Evaluations).

<Frame caption="Observability — Insights default landing">
  <img src="/images/v2/observability/01-insights.png" alt="Observability Insights dashboard" />
</Frame>

## What you can monitor

| Area | Examples |
| --- | --- |
| **Insights** | Success rate, policy blocks, tokens, **Cost (Phinite)**, incidents, alerts, agent health |
| **Sessions** | Filterable run list, export, open detail / Investigate |
| **Investigate** | Span · Timeline · Conversation + rubric / annotations |
| **Usage metrics** | Session counts, LLM/STT/TTS tokens, call duration |
| **Logs** | Node order, decision joints, variables |
| **Billing** | Spend by graph and environment |

<Note>
  Metrics and logs reflect **Agent Graph runs** along Design → Save → Build → Deploy. They are unrelated to [Agent Card](/agent-registry/overview) A2A identity. **Cost (Phinite)** on Insights is platform billable usage for the selected range.
</Note>

## Agent Graph runs

Every channel message, Chat API request, trigger webhook, or cron execution creates a **session**.

| Signal | Where |
| --- | --- |
| Fleet health | [Insights](/observability/insights) |
| Deep debug | [Investigate](/observability/investigate) |
| Execution timeline | [Session logs](/observability/logs/timeline) |
| Routing decisions | [Decision joints](/observability/logs/decision-joints) |
| Captured data | [Variables log](/observability/logs/variables) |
| Token spend | [Token usage](/observability/metrics/token-usage) |
| Voice duration | [Telephony metrics](/observability/metrics/telephony) |

## Debug workflow

1. Open **Observability** — start on [Insights](/observability/insights).
2. Set range and filters (channel, env, agent graph).
3. Drill into **Sessions**, open a session, then **Investigate** or classic [timeline](/observability/logs/timeline).
4. Fix the graph or tool, **Build**, and redeploy.

<Warning>
  PROD session logs may contain user PII. Restrict access via [RBAC](/user-management/user-roles).
</Warning>

## Related

- [Insights](/observability/insights)
- [Investigate](/observability/investigate)
- [Usage Metrics](/observability/usage-metrics)
- [Session Logs](/observability/logs)
- [Governance](/governance/overview)
- [Evaluations](/evaluations/overview)
