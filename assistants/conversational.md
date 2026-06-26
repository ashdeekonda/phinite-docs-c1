---
title: "Conversational Assistants (Voice & Chat)"
description: "Design chat and voice assistants using flows and intents across channels."
---

## Overview

Conversational assistants handle real-time chat and voice across channels. They use [Intents](/triggers-intents/intents) and [Agent Graphs](/assistants/components/flows).

## Channels

- [Web Chat](/integrations-hub/channels/webchat)
- [WhatsApp](/integrations-hub/channels/whatsapp)
- [Slack / Teams](/integrations-hub/channels/slack-teams)
- [Twilio Voice](/integrations-hub/channels/twilio)

## Design steps
<Frame>
  <img src="/images/CreateIntent.png" alt="Descriptive alt text" />
</Frame>

<Steps>
  <Step title="Define intents">
    Create intents and train prompts. See [Prompt Training](/triggers-intents/prompt-training).
  </Step>
  <Step title="Map to flows">
    Map intents to flows in [Mapping](/triggers-intents/mapping).
  </Step>
  <Step title="Connect channels">
    Configure channel authentication. See [Channels Overview](/integrations-hub/channels/overview).
  </Step>
</Steps>

<Tip>
  Use [Observability Logs](/observability/logs) to analyze conversation paths and refine intents.
</Tip>