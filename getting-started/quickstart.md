---
title: "Quick Start"
description: "Build and deploy your first AI assistant in minutes using Phinite Aura and Graph Studio."
---

# Quick Start

This guide walks you through creating your first assistant using **Phinite Aura** and **Graph Studio**.

In a few minutes, you'll have a working assistant that can understand intents, trigger tools, and reply naturally.

**Quickstart Video Tutorial Link**

<iframe src="https://www.youtube.com/embed/Pe8zjW3Qfg0" title="YouTube video player" frameborder="0" className="w-full aspect-video rounded-xl" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen />

## Before You Begin

You should already have:

- A verified **Phinite account**
- Access to a **workspace**
- Permission to create assistants in that workspace

<Note>
  New to workspaces? See [Workspace overview](/workspaces/workspace-overview). On Workspace Home, use **How to ship** beside **My Assistants** for guided journeys.
</Note>

---

## Step 1 — Open Phinite Aura

From Workspace Home, create a **New Assistant** or open an existing one and go to **Graph Studio**.

In the studio left rail, open **Phinite Aura** and describe what you want to build:

```text
Build an agent graph that answers FAQs and creates tickets in Zendesk.
```

Aura interprets your prompt, asks clarifying questions, and drafts your agent graph on the canvas.

---

## Step 2 — Graph Studio creates your agent graph

Aura updates **Graph Studio** in real time. Each node represents a reasoning or action step.

<Steps>
  <Step title="Assistant is created">
    A new assistant is added to your workspace with a unique ID.
  </Step>
  <Step title="Nodes appear on canvas">
    The agent graph structure is generated from your prompt.
  </Step>
  <Step title="Tools are connected">
    Mentioned systems (for example Zendesk) link to tools via **Integrations → Predefined tools** and Dev Studio.
  </Step>
</Steps>

---

## Step 3 — Test your agent graph

When the graph is ready, click **Test** in the studio toolbar.

<Steps>
  <Step title="Open the chat panel">
    Graph Studio shows a live test chat window.
  </Step>
  <Step title="Send test messages">
    Try a query like "Where is my latest order?"
  </Step>
  <Step title="Watch execution logs">
    Node-by-node execution appears in the timeline.
  </Step>
  <Step title="Save as Version">
    When testing passes, use **Save as Version** to publish a saved version of the agent graph (and tools as needed).
  </Step>
</Steps>

---

## Step 4 — Deploy to production

Promote a tested graph through **Builds** and channels.

<Steps>
  <Step title="Create an intent or trigger">
  Conversational and email assistants use **Intents**; autonomous assistants use **Triggers**. Attach the intent or trigger to your agent graph.
  </Step>
  <Step title="Open Builds">
    Under assistant **Deploy → Builds**, create a build by selecting the intent/trigger, agent graph version, and tool versions.
  </Step>
  <Step title="Assign build">
    Assign the build to Dev, UAT, or Production.
  </Step>
  <Step title="Add a channel">
    Under **Integrations → Channels**, connect webchat, chat, or voice and select the assistant and build. (Not required for all autonomous flows.)
  </Step>
</Steps>

---

## Troubleshooting

| Issue | Resolution |
| --- | --- |
| Aura doesn't respond | Refresh the workspace or check connectivity. |
| Blank canvas | Ensure you have permission to edit agent graphs. |
| Test messages fail | Verify tools and integrations are configured. |

<Warning>
  If you see an "Integration Limit" message, upgrade your workspace for additional tool connections.
</Warning>

---

## Next Steps

- [Graph Studio overview](/graph-studio/overview)
- [DevStudio overview](/devstudio/overview)
- [Observability overview](/observability/overview)
- [User roles](/user-management/user-roles)
