---
title: "Conversational Assistants (Voice & Chat)"
description: "Design chat and voice assistants using flows and intents across channels."
---

## Overview

Conversational assistants handle real-time chat and voice across channels. They use [Intents](/triggers-intents/intents-guide) and [Agent Graphs](/concepts/overview#agent-graphs).

## Channels

- [Web Chat](/channels/guide#webchat)
- [WhatsApp](/channels/guide#whatsapp)
- [Slack / Teams](/channels/guide#slack-and-teams)
- [Twilio Voice](/channels/guide#twilio)

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
    Configure channel authentication. See [Channels Overview](/channels/guide).
  </Step>
</Steps>

<Tip>
  Use [Observability Logs](/observability/logs) to analyze conversation paths and refine intents.
</Tip>