---
title: Intents
description: Define and manage the actions your assistant understands and responds to.
---

# Intents

Intents represent what the user wants to do. Each intent captures the purpose of a message and links it to the correct flow or action in your assistant.

<Info>
Intents act as routing logic for your assistant. They determine which flow or tool should run based on user input.
</Info>

---

## Overview

An intent consists of:
- **Name** – Identifies the intent.
- **Description** – Explains the intent’s purpose.
- **Training phrases** – Example utterances used to recognize user goals.
- **Connected flow** – The flow triggered when this intent is matched.

---

## Create an Intent

You can create intents manually or generate them automatically with AI prompts.

<Steps>
  <Step title="Go to Assistants → Components → Intents." />
  <Step title="Click Create Intent." />
  <Step title="Enter the Intent Name and Description." />
  <Step title="Select AI Prompt Generation to auto-generate examples." />
  <Step title="Review and edit the generated samples." />
  <Step title="Connect this intent to a specific Flow or Action." />
</Steps>

---

## AI Prompt Generation

Use AI-assisted generation to speed up training phrase creation.  
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
  <Step title="Open the Intent Testing tab." />
  <Step title="Enter a user message." />
  <Step title="Review the detected intent and confidence score." />
  <Step title="Adjust the examples if detection is inaccurate." />
</Steps>

<Info>
Testing helps ensure your assistant correctly interprets real-world messages before launch.
</Info>

---

## Manage Intents

| Action | Description |
|---------|--------------|
| **Edit** | Update name, description, or phrases |
| **Duplicate** | Create a variant of an existing intent |
| **Archive** | Disable without deleting |
| **Delete** | Remove permanently from the workspace |

---

## Link Intents to Flows

Once an intent is created, connect it to:
- A **flow** to drive conversation logic  
- A **tool** for backend integration  
- Another **assistant** for complex routing

<Info>
Linking ensures that every recognized intent leads to an actionable result.
</Info>

---

## Related Topics

- [Flows](/assistants/components/flows)
- [Triggers](/assistants/components/triggers)