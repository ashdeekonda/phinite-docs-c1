---
title: "Triggers (Autonomous)"
description: "Configure triggers to start agent graphs automatically or from external systems."
---

Triggers define how and when an autonomous assistant's agent graph begins. Configure them to start on demand via API, on a schedule, or from integration events.

<Frame>
  ![Triggers](/images/Triggers.png)
</Frame>

<Info>
  Triggers connect your assistant to external workflows and automation systems. Conversational and email assistants use [Intents](/triggers-intents/intents) instead.
</Info>

---

## Trigger types

Phinite supports three trigger types for autonomous assistants.

<Accordion title="API-based trigger">
  External applications start a specific agent graph via HTTP POST.

  **Use when:** A form submission, webhook, or external event needs immediate action.

  **Configuration:** Requires a workspace-level API key. See [Trigger APIs](/triggers-intents/triggers/api-guide) for endpoint details.

  **Best for:** Fast, real-time executions that complete within seconds.
</Accordion>

<Accordion title="Background task">
  Long-running executions that return immediately and track status asynchronously.

  **Use when:** The workflow may exceed standard API timeout limits.

  **Best for:** Heavy processing, multi-step jobs, or operations that need status polling.
</Accordion>

<Accordion title="Scheduler-based trigger">
  Flows start at fixed intervals or specific times (hourly, daily, weekly, or custom cron).

  **Use when:** You need periodic automation — daily reports, nightly syncs, batch processing.

  **Best for:** Recurring background processes that do not require an immediate response.
</Accordion>

---

## Choose the right trigger

| Scenario | Recommended trigger | Reason |
| --- | --- | --- |
| External app sends an event needing immediate action | **API-based** | Instant activation with minimal latency |
| Long-running workflow that may exceed API timeout | **Background task** | Track progress via status API |
| Recurring reports, syncs, or batch jobs | **Scheduler-based** | Automates repetition without manual calls |

---

## Configure a trigger

<Steps>
  <Step title="Open Triggers in your assistant">
    In the assistant sidebar under **Build**, select **Triggers**.
  </Step>
  <Step title="Click New Trigger">
    Select the trigger type (API, Background Task, or Scheduler).
  </Step>
  <Step title="Choose integration (if applicable)">
    The API URL adjusts for integration funnels (for example, `/jira` for Jira webhooks).
  </Step>
  <Step title="Choose the target agent graph">
    Select which graph this trigger should start.
  </Step>
  <Step title="Save, attach to build, and test">
    Validate in your development environment before promoting to production.
  </Step>
</Steps>

<Card title="Tip">
  Use scheduler-based triggers for long-running workflows. Use API triggers for short, transactional events.
</Card>

---

## Workspace API keys

API-based triggers depend on workspace-level API keys for authentication.

<Info>
  Store and rotate keys securely. Never expose API keys in client-side code or public repositories.
</Info>

---

## Best practices

- Use **API triggers** for short, transactional events
- Use **background tasks** for long events (track via status API)
- Use **scheduler triggers** for recurring jobs
- Avoid attaching multiple triggers to the same graph unless needed
- Test each trigger in development before deploying to production
- Validate incoming payloads and use idempotency keys where possible

---

## Monitoring

Review trigger executions in [Observability Logs](/observability/logs).

---

## Related topics

- [Trigger APIs](/triggers-intents/triggers/api-guide) — HTTP endpoints and payloads
- [Event-based triggers](/triggers-intents/event-triggers) — cron, email, and integration events
- [Mapping](/triggers-intents/mapping) — link triggers to agent graphs
- [Autonomous assistant guide](/assistants/autonomous)
- [Agent Graphs](/assistants/components/flows)
