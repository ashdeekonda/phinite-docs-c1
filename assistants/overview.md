---

## title: "Assistant Overview"
description: "Understand assistant types, how they are powered by flows, and where to start."

# Assistants

Assistants are the core of Phinite. Everything revolves around them.  
They are intelligent, multi-skilled entities that automate conversations, workflows, and business operations across channels.

An **Assistant** brings together multiple components — **Flows, Intents, Triggers, Tools, Environments, Builds, and Copilot** — to function as a cohesive unit.  
Each component plays a distinct role in defining how the Assistant behaves, interacts, and executes tasks.

### Types of Assistants

An assistant is an AI-powered capability that handles user interactions or background tasks using your workflows and tools.

- **Conversational Assistants**: Chat and voice experiences
- **Email Assistants**: Inbox automation for triage and replies
- **Autonomous Assistants**: Scheduled or event-driven background jobs

![Assistant-Overview](/Types-assistant.png)

### Comparision


| Type           | Best for                   | Triggers             | Channels                                |
| -------------- | -------------------------- | -------------------- | --------------------------------------- |
| Conversational | Real-time chat/voice       | Intents, chat events | Web Chat, WhatsApp, Slack/Teams, Twilio |
| Email          | Asynchronous communication | Inbound email        | Email                                   |
| Autonomous     | Background automation      | Schedules, webhooks  | N/A                                     |


## 🧩 Core Architecture

The heart of the Assistant — a visual workflow created in **Flowgen Studio**.\ Flows connect intents, triggers, and tools to define your automation logic. Natural language or programmatic cues that tell the Assistant _what the user wants_.\ Each intent can be AI-generated and linked to a specific flow. Event-driven or scheduled conditions that start a workflow automatically.\ They can originate from APIs, system events, or predefined schedules. Hybrid initiators that combine intent detection with trigger logic.\ Ideal for scenarios where a user action and a system signal both control flow initiation. Reusable building blocks maintained by developers in **DevStudio**.\ They perform API calls, logic processing, or data transformations. Isolated spaces for development, testing, and production deployment.\ Each environment controls visibility, access, and execution logs. Snapshot versions of an Assistant. Builds preserve dependencies, flows, and configurations across environments for controlled release and rollback. AI-powered assistant that helps you generate flows, intents, and triggers in minutes.\ It understands context and recommends workflow blocks intelligently.

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

Navigate to your workspace and select **Create Assistant**. Choose between **Conversational**, **Autonomous**, or **System Triggered** assistants. Open **Flowgen Studio** to visually create the workflow using blocks. Each flow must be linked to a **Trigger** or **Intent** to define its entry point. Add logic or data connectors from **DevStudio**’s tool library. Assign environment settings for Dev, UAT, or Production. Finalize and publish the Assistant as a versioned build.

---

## 🤖 Copilot

Copilot accelerates assistant creation by generating flows, intents, and triggers using natural language.

### Usage

- Ask: *“Create a flow to schedule a site visit and confirm via email.”*
- Copilot will suggest the structure, tool connections, and agent messages.
- You can edit or refine before deploying.

Copilot understands workspace context, available tools, and prior builds.\ It’s ideal for quickly iterating complex workflows.

---

## 🧭 Summary

Assistants in Phinite unify conversation, automation, and integration into a single, agentic architecture.  
They connect human intent with machine precision — through flows, tools, and triggers — to deliver intelligent, observable, and scalable outcomes.

Everything in Phinite starts and ends with an Assistant.\ Design it well — and every automation across your workspace becomes effortless.

## Next steps

- Explore [Types of Assistants](/assistants/types)
- Review [Assistant Components](/assistants/components)
- Build your first flow in [Flowgen](/flowgen/overview)

