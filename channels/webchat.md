---
title: Web Chat
description: Embed web chat and configure appearance for a Conversational Agent Graph.
icon: "comments"
---

<Note>
  Web chat deploys a **Conversational Agent Graph** via an embed script. Create an **Agent Build** and use **Deploy to Channel** to map the widget to **DEV / UAT / PROD**.
</Note>

## Set up web chat

1. **Save** your Conversational Agent Graph and create an **Agent Build** ([Builds overview](/builds/overview)).
2. Open workspace **Integrations** → **Channels** → **Web Chat** (or the web chat option in your tenant).
3. Create a channel configuration — note webhook or embed settings for **Development** first.
4. In Graph Studio, **Deploy** → **Deploy to Channel** — select web chat and assign the build to **DEV**.
5. Add the embed script to your site (copy from the integration or deploy confirmation).
6. Configure appearance — colors, logo, position, and greeting copy in the channel settings.
7. Test the widget in DEV; promote build assignment to **UAT** / **PROD** when ready.

<Frame caption="Web chat channel configuration">
  <img src="/images/webchat.png" alt="Web chat integration settings" />
</Frame>

<Tip>
  Test in **DEV** before exposing the embed on production pages. Confirm env variables used by the graph resolve in the DEV column.
</Tip>

## Related

- [Deploy to channel](/agents/deploy-channel)
- [Supported channels](/channels/supported)
- [Build environments](/builds/environments)
