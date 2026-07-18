---
title: Integrations configuration
description: Channels, Integration Tools, and Triggers in the workspace hub and Studio.
---

## What this is

**Integrations** connect Agent Graphs to the outside world: messaging **Channels**, callable **Integration Tools**, and autonomous **Triggers** (API, Cron, background tasks).

Configuration happens in the workspace **Integrations** hub and can be scoped to a graph from Studio.

## Where in the product

| Surface | Path | Purpose |
| --- | --- | --- |
| Integrations hub | `.../integration?tab=channels` | Connect WhatsApp, Slack, Teams, email, voice, web chat, … |
| Integration Tools | `.../integration?tab=predefined-tools` | App integrations used as tools |
| Triggers | `.../integration?tab=triggers` | API / Cron / conversational triggers |
| Studio Integrations | Studio → **Integrations** → Channels | Graph-scoped channel connections |
| Studio Triggers | Studio → **Triggers** | Graph-scoped trigger links |

![Integrations hub](/images/v2/configure/01-integrations-hub.png)

## Steps — connect a channel

1. Open workspace **Integrations** → **Channels** tab (or sidebar **Channels**).
2. Click **New Integration** / pick a channel type.
3. Complete credential and webhook configuration for **Development** first.
4. In Studio, **Deploy** → **Deploy to Channel** and assign your build ([Deploy to channel](/agents/deploy-channel)).

## Steps — configure a trigger

1. Open **Integrations** → **Triggers** tab.
2. Create **Autonomous** (API / Cron) or **Conversational** trigger as needed.
3. Assign a **Build** to DEV / UAT / PROD on the trigger connection.
4. Copy the webhook URL or cron schedule from the trigger config page.

## Studio shortcut

Studio → **Integrations** submenu lists **Channels** and **Integration Tools** without leaving the canvas. **Triggers** panel links to **Add trigger in Integrations** when none exist.

## Related

- [Deploy](/agents/deploy)
- [Deploy to channel](/agents/deploy-channel)
- [Deploy a trigger](/agents/deploy-trigger)
- [Configuration overview](/configure/overview)
