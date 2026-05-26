---
title: "Quick Start"
description: "Build and deploy your first AI assistant in minutes using Phinite Aura and Graph Studio."
---

# Quick Start

This guide walks you through creating your first AI Assistant using **Aura** and **Graph Studio**.

In a few minutes, you’ll have a working assistant that can understand intents, trigger tools, and reply naturally.

**Quickstart Video Tutorial Link**

<iframe src="https://www.youtube.com/embed/Pe8zjW3Qfg0" title="YouTube video player" frameborder="0" className="w-full aspect-video rounded-xl" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen />

## Before You Begin

You should already have:

- A verified **Phinite account**
- Access to a **workspace** (automatically created at signup)
- The **Copilot** interface visible on your workspace home screen

<Note>
  If you haven’t signed up yet, start here → [Signing Up](/setup-account/signing-up)
</Note>

---

## Step 1 — Open Phinite Aura

When you log into your workspace, you’ll see the **Aura's input bar** at the top.\
Type what you want to build.

```text
Build an agent graph that answers FAQs and creates tickets in Zendesk.
```

Aura interprets your prompt, asks clarifying questions, and starts creating your agent graph.

---

## Step 2 — Graph Studio Creates Your Agent Graph

Aura triggers **Graph Studio**, where your logic appears in real time.\
Each node represents a reasoning or action step.

<Steps>
  <Step title="Assistant is created">
    Copilot defines a new Assistant with a unique ID inside your workspace.
  </Step>
  <Step title="Nodes appear on canvas">
    The agent graph structure is generated instantly based on your intent.
  </Step>
  <Step title="Tools are connected">
    Any mentioned systems (like Zendesk) are auto-linked via DevStudio integrations.
  </Step>
</Steps>

---

## Step 3 — Test your Agent Graph

When the graph is ready, click **Test Agent Graph(top right corner)** to start testing.

<Steps>
  <Step title="Open the chat panel">
    Your graph studio shows a live chat window.
  </Step>
  <Step title="Send test messages">
    Try a query like Where is my latest order?.
  </Step>
  <Step title="Watch execution logs">
    Node-by-node execution appears in the timeline.
  </Step>
  <Step title="Publish your Agent">
    Once testing is complete, publish your tools and the agent graph.
  </Step>
</Steps>

---

## Step 4 — Deploy to Production

Once your agent passes testing, promote it to the **Production Environment**.

<Steps>
  <Step title="Create an intent or trigger based on your assistant type.">
    Attach the particular intent to your agent graph.
  </Step>
  <Step title="Open Build Page">
    Create a build by selecting the intent, Agent Graphs (selected by default), and tools along with their versions.
  </Step>
  <Step title="Click Create Build">
    Attach build to desired environment.
  </Step>
  <Step title="Add the assistant to channel">
    Select a deployment channel — web, chat, or voice — and choose the assistant. The build you created for that assistant will be used in the selected channel. (This step is not required for autonomous assistants.)
  </Step>
</Steps>

---

## Troubleshooting

| Issue | Resolution |
| --- | --- |
| Aura doesn't respond | Refresh the workspace or check connectivity. |
| GraphStudio shows blank canvas | Ensure you have permissions to create assistants. |
| Test messages fail | Verify DevStudio tools are configured properly. |

<Warning>
  If you see an “Integration Limit” message, upgrade your workspace to **Pro** for multi-tool support.
</Warning>

---

## Next Steps

<Steps>
  <Step title="Explore GraphStudio Studio">
    Learn how to customize agent graph visually → Graph Studio Overview
  </Step>
  <Step title="Build Custom Tools">
    Extend your assistant with APIs and data sources → DevStudio Overview
  </Step>
  <Step title="Monitor Interactions">
    View logs, performance, and usage → Observability Overview
  </Step>
</Steps>

---