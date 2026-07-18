---
title: Deploy a trigger
description: Run autonomous builds via API or Cron.
---

Triggers start Autonomous (and some Conversational) runs without a live chat UI.

## Types

| Type | Use |
| --- | --- |
| **API** | On-demand HTTP webhook |
| **Cron job** | Recurring schedule |
| **Background task** | Long-running / queued work (where available) |

## Steps

1. Create a **Build**.
2. In Studio, click **Deploy** → **Deploy as API** or **Cron job**.
3. Or open Studio → **Triggers** → **Add trigger in Integrations**.
4. Create the trigger connection; set workflow type.
5. Assign the build to DEV / UAT / PROD on the trigger.
6. Call the webhook or wait for the schedule.

![Triggers](/images/v2/deploy/02-triggers-sidebar.png)

## Related

- [Deploy](/agents/deploy)
- [Environments](/agents/environments)
