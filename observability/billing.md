---
title: "Billing Dashboard"
description: "Understand costs across tokens, telephony, and infrastructure for Agent Graph workloads."
---

The **Billing** dashboard aggregates spend from Agent Graph runs—LLM tokens, speech services, telephony, and related infrastructure.

## Views

- Costs by **Agent Graph** and environment (DEV / UAT / PROD)
- Token, telephony, and runtime breakdowns
- Trends over time and budget pacing

## Best practices

1. Set budgets and alerts before promoting builds to Prod.
2. Correlate cost spikes with [release notes](/reference/release-notes) and deploy dates.
3. Optimize tool-call frequency and model choices on hot graph paths.

<Note>
  Billing reflects workspace usage metering, not per-user [workspace RBAC](/user-management/user-management) roles.
</Note>

## Related

- [Token usage](/observability/metrics/token-usage)
- [Telephony metrics](/observability/metrics/telephony)
