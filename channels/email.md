---
title: "Email"
description: "Configure email channel for inbound/outbound message handling."
icon: "envelope"
---

## Setup

Configure email under **Integrations → Channels** in the workspace sidebar.

<Frame>
  ![Email](/images/email.png)
</Frame>

<Steps>
  <Step title="Open Integrations">
    Workspace sidebar → **Integrations** → **Channels** tab.
  </Step>
  <Step title="Connect provider">
    Configure SMTP/IMAP or provider API for the email channel.
  </Step>
  <Step title="Map to assistant">
    Assign the channel to an assistant and build for your target environment.
  </Step>
</Steps>

<Tip>
  Sanitize HTML and attachments before processing.
</Tip>