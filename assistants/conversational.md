---
title: "Conversational Assistants (Voice & Chat)"
description: "Design chat and voice assistants using flows and intents across channels."
---

## Overview

Conversational assistants handle real-time chat and voice across channels. They use [Intents](/triggers-intents/intents) and [Flows](/assistants/components/flows).

## Channels

- [Web Chat](/channels/webchat)
- [WhatsApp](/channels/whatsapp)
- [Slack / Teams](/channels/slack-teams)
- [Twilio Voice](/channels/twilio)

## Design steps
<Frame>
  <img src="/CreateIntent.png" alt="Descriptive alt text" />
</Frame>

<Steps>
  <Step title="Define intents">
    Create intents and train prompts. See [Prompt Training](/triggers-intents/prompt-training).
  </Step>
  <Step title="Map to flows">
    Map intents to flows in [Mapping](/triggers-intents/mapping).
  </Step>
  <Step title="Connect channels">
    Configure channel authentication. See [Channel Configuration](/channels/configuration).
  </Step>
</Steps>

<Tip>
  Use [Observability Logs](/observability/logs) to analyze conversation paths and refine intents.
</Tip>