---
title: "Assistant Overview"
description: "Understand assistant types, how they are powered by flows, and where to start."
---

# Assistants

Assistants are the core of Phinite. Everything revolves around them.\
They are intelligent, multi-skilled entities that automate conversations, workflows, and business operations across channels.

An **Assistant** brings together multiple components — **Flows, Intents, Triggers, Tools, Environments, Builds, and Copilot** — to function as a cohesive unit.\
Each component plays a distinct role in defining how the Assistant behaves, interacts, and executes tasks.

### Types of Assistants

An assistant is an AI-powered capability that handles user interactions or background tasks using your workflows and tools.

- **Conversational Assistants**: Chat and voice experiences
- **Email Assistants**: Inbox automation for triage and replies
- **Autonomous Assistants**: Scheduled or event-driven background jobs

<Frame>
  ![Assistant-Overview](/Types-assistant.png)
</Frame>

### Comparision

| Type           | Best for                   | Triggers             | Channels                                |
| :------------- | :------------------------- | :------------------- | :-------------------------------------- |
| Conversational | Real-time chat/voice       | Intents, chat events | Web Chat, WhatsApp, Slack/Teams, Twilio |
| Email          | Asynchronous communication | Inbound email        | Email                                   |
| Autonomous     | Background automation      | Schedules, webhooks  | N/A                                     |

## 🧩 Core Architecture

<CardGroup cols={2}>
  <Card title="Flows" icon="FlowArrow">
    The heart of the Assistant — a visual workflow created in **Flowgen Studio**.\
    Flows connect intents, triggers, and tools to define your automation logic.
  </Card>
  <Card title="Intents" icon="ChatText">
    Natural language or programmatic cues that tell the Assistant _what the user wants_.\
    Each intent can be AI-generated and linked to a specific flow.
  </Card>
  <Card title="Triggers" icon="hand-pointing">
    Event-driven or scheduled conditions that start a workflow automatically.\
    They can originate from APIs, system events, or predefined schedules.
  </Card>
  <Card title="Trigger Intents" icon="PlugZap">
    Hybrid initiators that combine intent detection with trigger logic.\
    Ideal for scenarios where a user action and a system signal both control flow initiation.
  </Card>
  <Card title="Tools" icon="Wrench">
    Reusable building blocks maintained by developers in **DevStudio**.\
    They perform API calls, logic processing, or data transformations.
  </Card>
  <Card title="Environments" icon="Server">
    Isolated spaces for development, testing, and production deployment.\
    Each environment controls visibility, access, and execution logs.
  </Card>
  <Card title="Builds" icon="Hammer">
    Snapshot versions of an Assistant. Builds preserve dependencies, flows, and configurations across environments for controlled release and rollback.
  </Card>
  <Card title="Copilot" icon="Sparkles">
    AI-powered assistant that helps you generate flows, intents, and triggers in minutes.\
    It understands context and recommends workflow blocks intelligently.
  </Card>
</CardGroup>

---

## ⚙️ How an Assistant Works

Each Assistant operates as a closed loop of logic and action.

1. **Trigger or Intent fires**
   - Initiates a **Flow**.
2. **Flow executes**
   - Moves across blocks — Agent, Tool, Logic, or Connector.
3. **Tools perform operations**
   - API calls, data validation, transformations.
4. **Responses return to the user or system**
   - Completing the workflow cycle.
5. **Logs and observability**
   - All executions are tracked under the **Environment** dashboard.

---

## 💡 Creating an Assistant

<Steps>
  <Step title="Go to Assistants → Create Assistant">
    Navigate to your workspace and select **Create Assistant**.
  </Step>
  <Step title="Define Type">
    Choose between **Conversational**, **Autonomous**, or **System Triggered** assistants.
  </Step>
  <Step title="Design Flows">
    Open **Flowgen Studio** to visually create the workflow using blocks.
  </Step>
  <Step title="Link Intents or Triggers">
    Each flow must be linked to a **Trigger** or **Intent** to define its entry point.
  </Step>
  <Step title="Attach Tools">
    Add logic or data connectors from **DevStudio**’s tool library.
  </Step>
  <Step title="Configure Environments">
    Assign environment settings for Dev, UAT, or Production.
  </Step>
  <Step title="Build and Deploy">
    Finalize and publish the Assistant as a versioned build.
  </Step>
</Steps>

---

## 🤖 Copilot

Copilot accelerates assistant creation by generating flows, intents, and triggers using natural language.

### Usage

- Ask: _“Create a flow to schedule a site visit and confirm via email.”_
- Copilot will suggest the structure, tool connections, and agent messages.
- You can edit or refine before deploying.

<Note>
  Copilot understands workspace context, available tools, and prior builds.\
  It’s ideal for quickly iterating complex workflows.
</Note>

---

## 🧭 Summary

Assistants in Phinite unify conversation, automation, and integration into a single, agentic architecture.\
They connect human intent with machine precision — through flows, tools, and triggers — to deliver intelligent, observable, and scalable outcomes.

<Note>
  Everything in Phinite starts and ends with an Assistant.\
  Design it well — and every automation across your workspace becomes effortless.
</Note>

## Next steps

- Explore [Types of Assistants](/assistants/types)
- Review [Assistant Components](/assistants/components)
- Build your first flow in [Flowgen](/flowgen/overview)