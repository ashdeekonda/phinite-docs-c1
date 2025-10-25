---
title: "Email"
description: "Configure email channel for inbound/outbound message handling."
icon: "envelope"
---

## Setup

<Frame>
  ![Email](/images/email.png)
</Frame>

<Steps>
  <Step title="Connect provider">
    Configure SMTP/IMAP or provider API.
  </Step>
  <Step title="Inbound routing">
    Route inbound emails to your channel endpoint.
  </Step>
  <Step title="Assistant mapping">
    Map inbound messages to assistants.
  </Step>
</Steps>

<Tip>
  Sanitize HTML and attachments before processing.
</Tip>