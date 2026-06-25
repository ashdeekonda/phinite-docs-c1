---
title: "Intents (Email Assistants)"
description: "Very similar to Conversational Intents, but differs in a few key logics. "
---

## Overview

An intent consists of:

- **Name** – Identifies the intent.
- **Intent Phrase** – Explains the intent’s purpose and utterances used to recognize user goals.
- **Funnel Down the Emails**– These includes basic and advanced filters.
- **Integration Funnel** – Email channel credentials that you want to connect with.
- **Connected Agent Grpah** – The graph triggered when this intent is matched.

---

## Create an Intent

<Steps>
  <Step title="Go to Assistants → Components → Intents.">
  </Step>
  <Step title="Click New Intent.">
  </Step>
  <Step title="Enter the Intent Name and Phrase.">
  </Step>
  <Step title='Write some basic purpose to utilize "refine prompt".'>
  </Step>
  <Step title="Review and edit the generated samples.">
  </Step>
  <Step title="Include basic and advanced filters">
  </Step>
  <Step title="Select the desired email channel configuration.">
  </Step>
  <Step title="Connect this intent to a specific Agent Graph.">
  </Step>
</Steps>

---

## AI Prompt Generation

Use AI-assisted generation to speed up training phrase creation.\
You can describe your intent naturally and let the system produce the structured output.

**Example Prompt:**

> Generate an intent for users who want to track their order delivery.

The AI will return:

- Suggested name
- Example utterances
- Description

<Card title="Tip">
  Write your prompts clearly. Focus on user goals, not system responses.
</Card>

---

## Manage Intents

| Action | Description |
| --- | --- |
| **Edit** | Update name, connected graphs, filters, integration or phrases |
| **Archive** | Disable without deleting |

---

## Related Topics

- [Agent Graphs](/concepts/overview#agent-graphs)
- [Triggers](/concepts/overview#intents-and-triggers)