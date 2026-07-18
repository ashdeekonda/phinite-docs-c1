---
title: Triggers & automation overview
description: Start Autonomous Agent Graph runs via API webhooks, cron schedules, and event-driven triggers.
icon: bolt
---

**Triggers** start **Autonomous Agent Graph** runs — webhooks, cron schedules, background tasks, and integration events invoke a pinned build without a live user session.

<CardGroup cols={2}>
  <Card title="Triggers hub" icon="bolt" href="/triggers-intents/triggers/overview">
    API, cron, and background-task trigger types.
  </Card>
  <Card title="Deploy a trigger" icon="paper-plane" href="/agents/deploy-trigger">
    Wire a build to API or Cron ingress from Graph Studio.
  </Card>
  <Card title="Autonomous graphs" icon="robot" href="/agents/autonomous">
    Design background automation on the canvas.
  </Card>
  <Card title="Event triggers" icon="calendar" type="note" href="/triggers-intents/event-triggers">
    React to integration and platform events.
  </Card>
</CardGroup>

<Info>
  **Conversational** Agent Graphs use **channels** and **Chat API** for ingress — not triggers. See [Channels overview](/channels/overview) and [Conversational graphs](/agents/conversational).
</Info>

## How automation starts

```mermaid
flowchart LR
  ingress[Trigger ingress]
  build[Pinned build]
  graph[Agent Graph run]
  logs[Observability logs]

  ingress --> build --> graph --> logs
```

| Ingress | Graph type | Deploy path |
| --- | --- | --- |
| **API webhook** | Autonomous | Deploy → **Deploy as API** |
| **Cron schedule** | Autonomous | Deploy → **Cron job** |
| **Background task** | Autonomous | Triggers hub configuration |
| **Channel message** | Conversational | Deploy → **Deploy to Channel** |
| **Chat API POST** | Conversational | Deploy → **Deploy as Chat API** |

## Trigger types

| Type | Use when | Doc |
| --- | --- | --- |
| **API (webhook)** | External system POSTs a payload | [Trigger API](/triggers-intents/triggers/api) |
| **Cron** | Fixed schedule execution | [Cron triggers](/triggers-intents/triggers/cron) |
| **Background task** | Queued or async runs | [Background task](/triggers-intents/triggers/bg_task) |
| **Event-based** | Integration or platform events | [Event triggers](/triggers-intents/event-triggers) |

See [Triggers overview](/triggers-intents/triggers/overview) for configuration details and [Trigger API guide](/triggers-intents/triggers/api-guide) for request formats.

## Configure and deploy

1. Design an **Autonomous** Agent Graph in [Graph Studio](/graph-studio/overview).
2. **Save** and **Build** — pin tool versions ([Builds](/builds/overview)).
3. Assign the build to **DEV** / **UAT** / **PROD**.
4. Connect trigger credentials under workspace **Integrations** if needed ([Configure integrations](/configure/integrations)).
5. Click **Deploy** in Graph Studio → **Deploy as API** or **Cron job**.
6. Copy the webhook URL or confirm the cron expression.
7. Monitor runs in [Observability](/observability/overview).

<Frame caption="Integrations hub — Triggers tab for Autonomous deploy">
  <img src="/images/Integrations-Overview.png" alt="Workspace Integrations with Triggers tab" />
</Frame>

## Mapping triggers to graphs

Use [Trigger mapping](/triggers-intents/mapping) to associate trigger definitions with specific Agent Graph builds per environment.

<Tip>
  Design Autonomous graphs for **idempotent** actions — webhooks may retry. Capture trigger payload fields as variables for auditability in logs.
</Tip>

## Related

- [Autonomous Agent Graphs](/agents/autonomous)
- [Deploy](/agents/deploy)
- [Integration funnel](/triggers-intents/triggers/integration-funnel)
- [Configure overview](/configure/overview)
