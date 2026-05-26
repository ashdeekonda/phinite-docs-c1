---
title: "Billing Dashboard"
description: "Understand costs across tokens, telephony, and infrastructure."
---

## Views

- Costs by assistant and environment
- Token, telephony, and runtime breakdowns
- Trends over time

## Bring Your Own Key (BYOK)

When agent nodes use **Model Keys** (customer provider credentials), platform **token and media costs** for those runs are excluded from Phinite billing aggregation (`ownKey` events). You still pay your cloud provider directly.

See **[Billing with BYOK](/byok/billing-and-usage)** for plan entitlements and observability notes.

## Best practices

- Set budgets and alerts
- Correlate cost spikes with releases
- Optimize tool calls and model choices
- Tag flows that use BYOK vs Phinite Key when reviewing usage
