---
title: "Quick Start"
description: "Build and deploy your first AI assistant in minutes using Phinite Copilot and Flowgen Studio."
---

# Quick Start

This guide walks you through creating your first AI Assistant using **Copilot** and **Flowgen Studio**.

In a few minutes, you’ll have a working assistant that can understand intents, trigger tools, and reply naturally.

**Quickstart Video Tutorial Link**

<Frame>
<img
    src="images/Flows.png"
    alt="Phinite Copilot Quickstart overview"
    title=""
    className="mr-auto"
    style={{ width:"100%" }}
  />
  </Frame>
  


---

## Before You Begin

You should already have:

- A verified **Phinite account**
- Access to a **workspace** (automatically created at signup)
- The **Copilot** interface visible on your workspace home screen

<Note>
  If you haven’t signed up yet, start here → [Signing Up](/setup-account/signing-up)
</Note>

---

## Step 1 — Open Copilot

When you log into your workspace, you’ll see the **Copilot input bar** at the top.\
Type what you want to build.

```text
Build an assistant that answers FAQs and creates tickets in Zendesk.
```

Copilot interprets your prompt, asks clarifying questions, and starts creating your flow.

---

## Step 2 — Flowgen Creates Your Assistant

Copilot triggers **Flowgen Studio**, where your logic appears in real time.\
Each node represents a reasoning or action step.

<Steps>
  <Step title="Assistant is created">
    Copilot defines a new Assistant with a unique ID inside your workspace.
  </Step>
  <Step title="Nodes appear on canvas">
    The flow structure is generated instantly based on your intent.
  </Step>
  <Step title="Tools are connected">
    Any mentioned systems (like Zendesk) are auto-linked via DevStudio integrations.
  </Step>
</Steps>

---

## Step 3 — Test in Copilot Mode

When the flow is ready, click **Run in Copilot** to start testing.

<Steps>
  <Step title="Open the chat panel">
    Your workspace shows a live chat window.
  </Step>
  <Step title="Send test messages">
    Try a query like Where is my latest order?.
  </Step>
  <Step title="Watch execution logs">
    Node-by-node execution appears in the timeline.
  </Step>
</Steps>

---

## Step 4 — Deploy to Production

Once your assistant passes testing, promote it to the **Production Environment**.

<Steps>
  <Step title="Open Environment Panel">
    Switch from Dev to Production in the top navigation bar.
  </Step>
  <Step title="Click Deploy">
    Confirm build promotion and environment sync.
  </Step>
  <Step title="Add a Channel">
    Select a deployment channel — web, chat, voice, or API endpoint.
  </Step>
</Steps>

---

## Troubleshooting

| Issue                      | Resolution                                        |
| -------------------------- | ------------------------------------------------- |
| Copilot doesn't respond    | Refresh the workspace or check connectivity.      |
| Flowgen shows blank canvas | Ensure you have permissions to create assistants. |
| Test messages fail         | Verify DevStudio tools are configured properly.   |

<Warning>
  If you see an “Integration Limit” message, upgrade your workspace to **Pro** for multi-tool support.
</Warning>

---

## Next Steps

<Steps>
  <Step title="Explore Flowgen Studio">
    Learn how to customize flows visually → Flowgen Overview
  </Step>
  <Step title="Build Custom Tools">
    Extend your assistant with APIs and data sources → DevStudio Overview
  </Step>
  <Step title="Monitor Interactions">
    View logs, performance, and usage → Observability Overview
  </Step>
</Steps>

---