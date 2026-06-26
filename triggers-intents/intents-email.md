---
title: "Intents (Email)"
description: "Classify inbound email and route messages to the right agent graph."
---

Email assistants use intents to classify inbound mail and start the correct agent graph — similar to conversational intents, with additional email-specific filters and channel configuration.

---

## What an email intent includes

| Field | Description |
| --- | --- |
| **Name** | Identifies the intent |
| **Intent phrase** | Purpose and patterns used to classify email content |
| **Funnel filters** | Basic and advanced filters to narrow which emails match |
| **Integration funnel** | Email channel credentials (inbox connection) |
| **Connected agent graph** | The graph triggered when this intent matches |

---

## Create an email intent

<Steps>
  <Step title="Open Intents in your email assistant">
    In the assistant sidebar under **Build**, select **Intents**.
  </Step>
  <Step title="Click New Intent">
    Enter the intent name and phrase.
  </Step>
  <Step title="Refine with AI">
    Write a basic purpose and use **Refine prompt** to generate classification samples.
  </Step>
  <Step title="Configure filters">
    Add basic and advanced filters under **Funnel Down the Emails**. See [Email channel — funnel filters](/integrations-hub/channels/email#funnel-down-the-emails-intent-filters) for every filter type and match option.
  </Step>
  <Step title="Select email channel">
    Choose the inbox configuration from your integration funnel.
  </Step>
  <Step title="Connect an agent graph">
    Link the intent to the graph that processes matching mail.
  </Step>
</Steps>

---

## AI prompt generation

Describe the email scenario naturally:

> Generate an intent for customer emails asking about order delivery status.

Review the suggested name, example phrases, and description before saving.

<Card title="Tip">
  Focus on the sender's goal — not the reply your assistant will send.
</Card>

---

## Manage intents

| Action | Description |
| --- | --- |
| **Edit** | Update name, filters, connected graphs, integration, or phrases |
| **Archive** | Disable without deleting |

---

## Related topics

- [Conversational intents](/triggers-intents/intents) — chat and voice routing
- [Email assistant guide](/assistants/email)
- [Email channel](/integrations-hub/channels/email)
- [Agent Graphs](/assistants/components/flows)
