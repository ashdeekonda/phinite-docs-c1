---
title: "Usage Metrics"
description: "Track sessions, token usage, and telephony metrics for Agent Graph runs."
---

Usage metrics quantify how Agent Graphs consume platform resources after deploy.

<CardGroup cols={3}>
  <Card title="Session count" icon="users" href="/observability/metrics/session-count">
    Runs by graph, channel, and environment.
  </Card>
  <Card title="Token usage" icon="coins" href="/observability/metrics/token-usage">
    LLM, STT, and TTS consumption.
  </Card>
  <Card title="Telephony" icon="phone" href="/observability/metrics/telephony">
    Voice channel duration and quality.
  </Card>
</CardGroup>

## Best practices

- Alert on abnormal spikes after a new **Build** ships.
- Correlate metric shifts with deploys and integration changes.
- Break down by Agent Graph and environment before optimizing models or tools.

<Note>
  Filter dimensions use **Agent Graph** names—the top-level object you design in Graph Studio—not legacy assistant labels.
</Note>

## Related

- [Filtering & Search](/observability/filtering)
- [Billing Dashboard](/observability/billing)
