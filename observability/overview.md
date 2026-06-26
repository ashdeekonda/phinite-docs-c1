---
title: "Observability Overview"
description: "Monitor sessions, usage, performance, and errors across assistants, agent graphs, and tools."
---

The workspace **Observability** area opens on **Sessions** — a searchable list of assistant runs (chat, voice, and autonomous executions). Use it to inspect individual session logs, filter by time and environment, and drill into token and tool usage.

**Evaluations** is listed in the assistant Monitor nav and is coming soon for quality and performance scoring.

## What you can monitor

- **Sessions**: conversation and execution history per assistant
- **Usage Metrics**: sessions, tokens, telephony
- **Logs**: execution traces, decisions, variables
- **Filtering & Search**: slice data by time, user, assistant, environment
- **Billing & Usage**: understand costs and allocation

## Related

- [Usage Metrics](/observability/usage-metrics)
- [Session Logs & Analysis](/observability/logs)
- [Filtering & Search](/observability/filtering)
- [Billing & Usage](/observability/billing)

<Note>
**Developers:** session metadata is available at `GET /api/v1/logs-metadata`. Workspace utilization and billing aggregates use `GET /api/v1/utilization_v2/*` (see api-server OpenAPI at `/api-docs`).
</Note>