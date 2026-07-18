---
title: Quickstart
description: Empty workspace to a deployable agent build.
---

End-to-end path using current Graph Studio labels.

## Steps

1. Open **Workspace Home**.
2. Click **New Agent Graph**.
3. Enter **Agent Graph Name** and **Description**.
4. Choose **Conversational** or **Autonomous**.
5. Click **Create Agent Graph** (opens Graph Studio).
6. Design nodes; attach tools / RAG as needed.
7. Click **Save**.
8. Click **Build** → review graph + tools → **Create Build** (publish tools first if prompted).
9. Assign the build to **DEV** (then UAT / PROD when ready).
10. Click **Deploy** and pick a target:
    - Conversational: **Deploy as A2A**, **Deploy to Channel**, or **Deploy as Chat API**
    - Autonomous: **Deploy as API**, **Cron job**, or **Deploy as A2A** (coming soon)

![New Agent Graph](/images/v2/agents/01-new-agent-graph-modal.png)

## After first deploy

| Goal | Page |
| --- | --- |
| Channel webhooks | [Deploy to a channel](/agents/deploy-channel) |
| API / Cron | [Deploy a trigger](/agents/deploy-trigger) |
| Public A2A link | [Expose as A2A](/agents/expose-a2a) |

## Related

- [Build an agent graph](/agents/build-graph)
- [Builds](/agents/builds)
- [Deploy](/agents/deploy)
