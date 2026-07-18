---
title: Deploy to a channel
description: Assign a build to a channel environment and webhook.
---

Use this for Conversational agents on WhatsApp, Slack, Teams, web chat, voice, email, and similar channels.

## Steps

1. Connect the channel under workspace **Integrations** → **Channels** (or Studio → Integrations → Channels).
2. Create a **Build** for the agent graph.
3. In Studio, click **Deploy** → **Deploy to Channel**.
4. Pick the channel and environment (start with **Development**).
5. Assign the build so inbound messages run that exact build.
6. Message the channel to test before promoting to UAT / Production.

![Integrations hub](/images/v2/deploy/04-integrations-hub.png)

## Related

- [Deploy](/agents/deploy)
- [Environments](/agents/environments)
