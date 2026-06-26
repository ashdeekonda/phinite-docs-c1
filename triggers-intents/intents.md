---
title: "Intents (Conversational)"
description: "Define and manage the actions your conversational assistant understands and responds to."
---

Intents represent what the user wants to do. Each intent captures the purpose of a message and links it to the correct agent graph in your assistant.

<Info>
  Intents act as routing logic for conversational assistants. They determine which agent graph runs based on user input. If needed, the intent agent asks clarifying questions.
</Info>

<Frame>
  ![Intents](/images/intents.png)
</Frame>

---

## What an intent includes

| Field | Description |
| --- | --- |
| **Name** | Identifies the intent |
| **Intent phrase** | Purpose and utterances used to recognize user goals |
| **Connected agent graph** | The graph triggered when this intent is matched |
| **Enable trigger** | Optional API endpoint that starts a conversation in a selected channel using the connected graph |

---

## Create an intent

<Steps>
  <Step title="Open Intents in your assistant">
    In the assistant sidebar under **Build**, select **Intents**.
  </Step>
  <Step title="Click New Intent">
    Enter the intent name and phrase.
  </Step>
  <Step title="Refine with AI">
    Write a basic purpose and use **Refine prompt** to generate training samples. Review and edit the output.
  </Step>
  <Step title="Connect an agent graph">
    Link the intent to the graph that should handle this request.
  </Step>
  <Step title="Test before deploy">
    Use the Intent Testing tab to validate detection. See [Testing Intents](/triggers-intents/testing-intents).
  </Step>
</Steps>

---

## AI prompt generation

Describe your intent naturally and let the system produce structured output.

**Example prompt:**

> Generate an intent for users who want to track their order delivery.

The AI returns a suggested name, example utterances, and description.

<Card title="Tip">
  Write prompts that focus on user goals, not system responses. For deeper guidance, see [Prompt Training](/triggers-intents/prompt-training).
</Card>

---

## Test an intent

<Steps>
  <Step title="Open the Intent Testing tab" />
  <Step title="Enter a user message" />
  <Step title="Review the detected intent" />
  <Step title="Adjust the intent phrase if detection is inaccurate" />
</Steps>

<Check>
  Intents should achieve high precision and recall on test utterances before you attach them to a build.
</Check>

---

## Manage intents

| Action | Description |
| --- | --- |
| **Edit** | Update name, connected graphs, integration, or phrases |
| **Archive** | Disable without deleting |

---

## Map intents to flows

After creating intents, link them to agent graphs. See [Mapping](/triggers-intents/mapping).

<Tip>
  Iterate on training with real conversation data from [Observability Logs](/observability/logs).
</Tip>

---

## Related topics

- [Email intents](/triggers-intents/intents-email) — same concept with email filters and funnel
- [Intent as API](/triggers-intents/intent-as-api) — programmatic conversation start
- [Agent Graphs](/assistants/components/flows)
- [Triggers & Intents overview](/triggers-intents/overview)
