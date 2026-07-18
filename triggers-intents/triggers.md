---
title: Triggers
description: Start Autonomous Agent Graphs via webhooks, schedules, and event-based automation.
---

**Triggers** run **Autonomous Agent Graphs** (and some automation entry points) without a chat UI. They replace the legacy **Intents** nav — configure trigger type, assign an **Agent Build**, and invoke via HTTP or Cron.

<Note>
  For API payloads, auth, and execution modes, start at [Trigger APIs overview](/triggers-intents/triggers/overview). For Studio deploy steps, see [Deploy a trigger](/agents/deploy-trigger).
</Note>

<CardGroup cols={2}>
  <Card title="Trigger APIs" icon="code" href="/triggers-intents/triggers/overview">
    API, Background Task, and Cron execution modes.
  </Card>
  <Card title="Event triggers" icon="clock" href="/triggers-intents/event-triggers">
    Cron schedules and email-driven runs.
  </Card>
  <Card title="Mapping" icon="diagram-project" href="/triggers-intents/mapping">
    Connect triggers to Agent Builds per environment.
  </Card>
  <Card title="Integrations" icon="plug" href="/configure/integrations">
    Create triggers in the workspace hub.
  </Card>
</CardGroup>

## Trigger categories

| Category | Examples | Doc |
| --- | --- | --- |
| **HTTP / API** | Webhooks, synchronous calls, background tasks | [Trigger overview](/triggers-intents/triggers/overview) |
| **Scheduled** | Cron jobs on the platform | [Cron jobs](/triggers-intents/triggers/cron) |
| **Event-based** | Recurring sync, inbound email automation | [Event triggers](/triggers-intents/event-triggers) |
| **Integration funnel** | Jira and similar inbound event pipes | [Integration funnel](/triggers-intents/triggers/integration-funnel) |

<Frame caption="Studio Triggers panel — graph-scoped links to Integrations">
  <img src="/images/v2/deploy/02-triggers-sidebar.png" alt="Graph Studio Triggers sidebar" />
</Frame>

## Best practices

- Validate incoming payloads and reject malformed requests early.
- Use **idempotency keys** for webhook retries from external systems.
- Implement retries with backoff on the **caller** side for background task polling.
- Test in **DEV** with a workspace Bearer token before **PROD** promotion.
- Review trigger executions in [Observability logs](/observability/logs).

## Related

- [Deploy a trigger](/agents/deploy-trigger)
- [Triggers & automation overview](/triggers-intents/overview)
- [Build environments](/builds/environments)
