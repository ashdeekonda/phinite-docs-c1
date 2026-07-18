---
title: Deploy
description: Deploy a build to a channel, API, cron, or A2A.
---

After you have a **Build**, use **Deploy** in Graph Studio.

Deploy stays disabled until at least one build exists for the graph.

## Conversational targets

| Tab | Outcome |
| --- | --- |
| **Deploy as A2A** | Agent Card + hosted A2A URL |
| **Deploy to Channel** | Assign build to a connected channel environment |
| **Deploy as Chat API** | HTTP chat endpoint for backends/apps |

## Autonomous targets

| Tab | Outcome |
| --- | --- |
| **Deploy as API** | HTTP trigger webhook |
| **Cron job** | Scheduled runs |
| **Deploy as A2A** | Coming soon |

## Steps

1. Create a build ([Builds](/agents/builds)).
2. Click **Deploy**.
3. Choose a tab and follow the in-modal steps.
4. Finish channel/trigger config in **Integrations** if prompted.

## Where config lives

| Need | Go to |
| --- | --- |
| Channels / triggers hub | Workspace **Integrations** (Tools / Channels / Triggers) |
| Graph-scoped channels | Studio → **Integrations** → Channels |
| Graph-scoped triggers | Studio → **Triggers** |

![Integrations](/images/v2/deploy/03-integrations-menu.png)

## Related

- [Deploy to channel](/agents/deploy-channel)
- [Deploy trigger](/agents/deploy-trigger)
- [Expose as A2A](/agents/expose-a2a)
