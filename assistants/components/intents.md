---
title: "Intents (Conversational Assistant)"
description: "Define and manage the actions your assistant understands and responds to."
---

# Intents

Intents represent what the user wants to do. Each intent captures the purpose of a message and links it to the correct flow or action in your assistant.

<Info>
  Intents act as routing logic for your assistant. They determine which agent graph should run based on user input. If needed intent agent asks clarifying questions.
</Info>

---

## Overview

An intent consists of:

- **Name** – Identifies the intent.
- **Intent Phrase** – Explains the intent’s purpose and utterances used to recognize user goals.
- **Connected Agent Grpah** – The graph triggered when this intent is matched.
- **Enable Trigger** – Appears after creating the intent. This unique capability provides API endpoints that, when invoked, automatically start a conversation in the selected channel (configured through the integration funnel) using the connected agent graph.

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

## Test an Intent

You can test your intent directly within the console before deployment.

<Steps>
  <Step title="Open the Intent Testing tab.">
  </Step>
  <Step title="Enter a user message.">
  </Step>
  <Step title="Review the detected intent.">
  </Step>
  <Step title="Adjust the intent phrase if detection is inaccurate.">
  </Step>
</Steps>

<Info>
  Testing helps ensure your assistant correctly interprets real-world messages before launch.
</Info>

---

## Manage Intents

| Action | Description |
| --- | --- |
| **Edit** | Update name, connected graphs, integration or phrases |
| **Archive** | Disable without deleting |


---

## Related Topics

- [Agent Graphs](/assistants/components/flows)
- [Triggers](/assistants/components/triggers)