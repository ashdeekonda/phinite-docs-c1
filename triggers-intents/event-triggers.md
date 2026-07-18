---
title: Event-based triggers
description: Cron schedules and email-driven automation for Autonomous Agent Graphs.
---

**Event-based triggers** start **Autonomous Agent Graphs** on a schedule or when an external event occurs — without a user typing in a chat UI.

<Note>
  Platform **Cron jobs** are configured in **Integrations** → **Triggers** or via **Deploy** → **Cron job** in Graph Studio. Assign an **Agent Build** per **DEV / UAT / PROD**.
</Note>

## Trigger types

| Type | Behavior | Configuration |
| --- | --- | --- |
| **Cron** | Runs on a schedule inside Phinite | Set schedule in trigger UI — no external scheduler required |
| **Email** | Starts when inbound mail matches routing rules | Connect [Email channel](/channels/email) and map to a build |
| **Webhooks** | External systems POST to trigger URL | API or Background Task mode ([Trigger APIs](/triggers-intents/triggers/overview)) |

## Cron example

```cron
0 * * * *  # Run hourly
```

1. Create an **Agent Build** for the Autonomous Agent Graph.
2. Open **Integrations** → **Triggers** → create **Cron** trigger (or **Deploy** → **Cron job** in Studio).
3. Set the cron expression and initial **message** / **user_variables** if the UI exposes them.
4. Assign the build to **DEV**; wait for the first scheduled run or use platform logs to confirm.
5. Promote to **UAT** / **PROD** when validated.

<Tip>
  Design Cron flows to be **idempotent** — a missed or duplicate tick should not corrupt data. Use session variables to track last-run timestamps when needed.
</Tip>

<Warning>
  Long-running Cron graphs should use **Background Task** execution if invoked via API adjuncts; pure platform Cron runs the assigned build directly on schedule.
</Warning>

## Related

- [Cron jobs](/triggers-intents/triggers/cron)
- [Deploy a trigger](/agents/deploy-trigger)
- [Mapping triggers](/triggers-intents/mapping)
