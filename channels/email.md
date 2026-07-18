---
title: Email
description: Configure email as a channel for Conversational Agent Graphs.
icon: "envelope"
---

<Note>
  The workspace filter may still show an **Email** chip for legacy graphs. New **Agent Graphs** are created as **Conversational** or **Autonomous** only — email channel deploy applies to Conversational graphs handling inbound mail.
</Note>

## Set up email channel

1. Open workspace **Integrations** → **Channels** → **Email**.
2. Connect your provider — configure SMTP/IMAP or provider API credentials for **Development**.
3. Set inbound routing so new messages hit the Phinite channel endpoint (webhook or polling per your integration type).
4. **Save** your Conversational Agent Graph and create an **Agent Build**.
5. **Deploy** → **Deploy to Channel** — select email, assign build to **DEV**.
6. Send a test inbound email; confirm the Agent Graph session starts and replies as expected.
7. Promote build assignment to **UAT** / **PROD** when validated.

<Frame caption="Email channel configuration">
  <img src="/images/email.png" alt="Email channel integration settings" />
</Frame>

<Tip>
  Sanitize HTML bodies and scan attachments before passing content into Agent Graph nodes. Use env variables for provider secrets — never embed credentials in the graph.
</Tip>

## Related

- [Deploy to channel](/agents/deploy-channel)
- [Supported channels](/channels/supported)
- [Build environments](/builds/environments)
