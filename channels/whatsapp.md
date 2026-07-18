---
title: WhatsApp
description: Connect WhatsApp Business API for Conversational Agent Graphs.
icon: "whatsapp"
---

<Note>
  WhatsApp requires Business API credentials and a verified webhook. Assign an **Agent Build** per environment after the channel is connected in **Integrations**.
</Note>

## Set up WhatsApp

1. Obtain **WhatsApp Business API** credentials from Meta or your BSP.
2. Open workspace **Integrations** → **Channels** → **WhatsApp**.
3. Create a configuration — enter API tokens, phone number ID, and related fields for **Development**.
4. Copy the **DEV** webhook URL from the saved configuration.
5. In your WhatsApp / Meta developer console, point inbound message webhooks to that URL.
6. **Save** your Conversational Agent Graph and create an **Agent Build**.
7. In Graph Studio, **Deploy** → **Deploy to Channel** — select WhatsApp and assign the build to **DEV**.
8. Send a test message; verify the session in [Observability logs](/observability/logs).
9. Promote to **UAT** / **PROD** with environment-specific webhook URLs.

<Frame caption="WhatsApp channel integration">
  <img src="/images/chatbot-integration.png" alt="WhatsApp Business API channel setup" />
</Frame>

<Warning>
  Verify webhook signatures from Meta to prevent spoofed inbound messages.
</Warning>

## Related

- [Deploy to channel](/agents/deploy-channel)
- [Supported channels](/channels/supported)
- [Integrations configuration](/configure/integrations)
