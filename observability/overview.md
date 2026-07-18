---
title: Observability overview
description: Monitor usage, performance, and errors across Agent Graph runs, tools, and channels.
icon: chart-line
---

Observability surfaces how **Agent Graphs** behave in each environment — sessions, tokens, telephony, execution logs, and billing allocation.

<CardGroup cols={2}>
  <Card title="Usage metrics" icon="chart-line" href="/observability/usage-metrics">
    Sessions, tokens, and telephony KPIs.
  </Card>
  <Card title="Session logs" icon="list" href="/observability/logs">
    Timeline, decisions, and captured variables.
  </Card>
  <Card title="Filtering" icon="filter" href="/observability/filtering">
    Slice by graph, environment, channel, and time.
  </Card>
  <Card title="Billing" icon="credit-card" type="note" href="/observability/billing">
    Cost breakdowns tied to runtime usage.
  </Card>
</CardGroup>

## What you can monitor

| Area | Examples |
| --- | --- |
| **Usage metrics** | Session counts, LLM/STT/TTS tokens, call duration |
| **Logs** | Node execution order, branching decisions, tool failures |
| **Filtering** | Time range, Agent Graph, environment, channel, build version |
| **Billing** | Token and telephony spend by graph and environment |

<Note>
  Metrics and logs reflect **Agent Graph runs** along the Design → Save → Build → Deploy path. They are unrelated to [Agent Card](/agent-registry/overview) A2A identity or external registry discovery.
</Note>

## Agent Graph runs

Every channel message, Chat API request, trigger webhook, or cron execution creates a **session** — one full run of a pinned build in an environment.

| Signal | Where to find it |
| --- | --- |
| **Execution timeline** | [Session logs](/observability/logs/timeline) — node order and duration |
| **Routing decisions** | [Decision joints](/observability/logs/decision-joints) — conditional edge outcomes |
| **Captured data** | [Variables log](/observability/logs/variables) — inputs and outputs per node |
| **Token spend** | [Token usage](/observability/metrics/token-usage) — LLM/STT/TTS breakdown |
| **Voice duration** | [Telephony metrics](/observability/metrics/telephony) — call length and counts |

<Tip>
  Filter logs by **build version** when debugging after a deploy — compare behavior between builds in the same environment.
</Tip>

## Metrics at a glance

| Metric | Applies to |
| --- | --- |
| [Session count](/observability/metrics/session-count) | All graph types and ingress paths |
| [Token usage](/observability/metrics/token-usage) | LLM, STT, TTS consumption |
| [Telephony](/observability/metrics/telephony) | Voice channel runs |

See [Usage metrics](/observability/usage-metrics) for dashboard layout.

## Debug workflow

1. Open **Observability** from the workspace sidebar.
2. Set time range and filter by **Agent Graph**, **environment**, or **channel**.
3. Select a session to open the [timeline](/observability/logs/timeline).
4. Inspect failed tool nodes and captured variables.
5. Fix the graph or tool in Graph Studio, create a new **Build**, and redeploy.

<Warning>
  PROD session logs may contain user PII from channel messages. Restrict observability access via [RBAC](/user-management/user-roles).
</Warning>

## Related

- [Usage Metrics](/observability/usage-metrics)
- [Session Logs & Analysis](/observability/logs)
- [Filtering & Search](/observability/filtering)
- [Billing Dashboard](/observability/billing)
- [Builds overview](/builds/overview)
