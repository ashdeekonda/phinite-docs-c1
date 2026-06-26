# Assistants

Assistants are the core of Phinite. Everything revolves around them.\
They are intelligent, multi-skilled entities that automate conversations, workflows, and business operations across channels.

An **Assistant** brings together **Agent Graphs, Intents, Triggers, Tools, Environments, Builds, and Phinite Aura** to function as a cohesive unit.
Each component plays a distinct role in defining how the Assistant behaves, interacts, and executes tasks.

### Solution types

Phinite supports three assistant solution types — conversational, email, and autonomous. Each differs in how workflows start and which channels they use.

See **[Build on Phinite](/getting-started/what-you-can-build)** for a full comparison, use-case patterns, and links to type-specific guides. Quick reference:

| Type | Entry point | Channels |
| --- | --- | --- |
| Conversational | [Intents](/triggers-intents/intents) | Web Chat, WhatsApp, Slack, Teams, Twilio |
| Email | [Email intents](/triggers-intents/intents-email) | Email |
| Autonomous | [Triggers](/triggers-intents/triggers) | API, cron, webhooks |

<Frame>
  <img
    alt="Assistant Overview"
    title="Assistant Overview"
    lightAlt="Assistant Overview"
    darkAlt="Assistant Overview"
    src="/images/Assistant-Overview.png"
    className="dark:hidden"
  />
  <img
    alt="Assistant Overview"
    title="Assistant Overview"
    lightAlt="Assistant Overview"
    darkAlt="Assistant Overview"
    src="images/Assistant-Overview.png"
    className="hidden dark:block"
  />
</Frame>

## Assistant navigation (Build / Deploy / Monitor)

When you open an assistant, the sidebar is organised in three sections:

| Section | Items |
| --- | --- |
| **Build** | Overview, **Agent Graphs** (Graph Studio), **Tools** (Dev Studio), **Intents** (conversational/email) or **Triggers** (autonomous) |
| **Deploy** | **Builds**, **Env. variables**, **Agent Cards** (conversational and voice) |
| **Monitor** | **Observability** (sessions for this assistant), Evaluations (coming soon) |

---

## 🧩 Core Architecture

<CardGroup cols={2}>
  <Card title="Agent Graphs" icon="FlowArrow">
    The heart of the Assistant — a visual workflow created in **Graph Studio**.\
    AgentGraphs connect intents, triggers, and tools to define your automation logic.
  </Card>

  <Card title="Intents & Triggers" icon="bullseye" href="/triggers-intents/overview">
    Entry points that start agent graphs — intents for conversational and email assistants, triggers for autonomous. See the [Triggers & Intents](/triggers-intents/overview) guide.
  </Card>

  <Card title="Custom Tools" icon="Wrench">
    Reusable building blocks maintained by developers in **DevStudio**.\
    They perform complex logic implementation, data processing, heavy code operation or data transformations.
  </Card>

  <Card title="Environments" icon="Server">
    Isolated spaces for development, staging, and production deployment.\
    Each environment controls visibility, access, and execution logs. Utilized by custom tools.
  </Card>

  <Card title="Builds" icon="Hammer">
    Snapshot versions of an Assistant. Builds preserve dependencies, flows, and configurations across environments for controlled release and rollback. 
  </Card>

  <Card title="Phinite Aura" icon="Sparkles">
    AI-powered assistant that helps you generate agent graphs.\
    It understands context and build and edits agent nodes intelligently.
  </Card>

  <Card title="A2A (Agent-to-Agent)" icon="share-nodes" href="/agent-registry/overview">
    Expose published agent graphs as discoverable **Agent Cards**, browse the catalog, and compose multi-agent flows with **Browse** or **Discovery** registry nodes.
  </Card>
</CardGroup>

---

## ⚙️ How an Assistant Works

Each Assistant operates as a closed loop of logic and action.

1. **Trigger or Intent fires**
   - Initiates a **Agent Graph**.
2. **Agent Graph executes**
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
    Choose between **Conversational**, **Autonomous**, or \*\*Email \*\*assistants.
  </Step>
  <Step title="Design Agent Graph">
    Open **Graph Studio** to visually create the graph using Agents Node.
  </Step>
  <Step title="Link Intents or Triggers">
    Each flow must be linked to a **Trigger** or **Intent(depending on assistant type)** to define its entry point.
  </Step>
  <Step title="Attach Tools">
    Add logic or data connectors from **DevStudio**’s tool library.
  </Step>
  <Step title="Configure Environments">
    Assign environment settings for Dev, UAT, or Production.
  </Step>
  <Step title="Build and Deploy">
    Finalize and attach environment the Assistant as a versioned build.
  </Step>
</Steps>

---

## 🤖 Aura

Aura accelerates assistant creation by generating agent graphs, tools using natural language.

### Usage

- Ask: _“Create a flow to schedule a site visit and confirm via email.”_
- Aura will suggest and build the structure, tool connections, and agent messages.
- You can edit or refine before deploying.

---

## 🧭 Summary

Assistants in Phinite unify conversation, automation, and integration into a single, agentic architecture.\
They connect human intent with machine precision — through agent graph, tools, and triggers — to deliver intelligent, observable, and scalable outcomes.

<Note>
  Everything in Phinite starts and ends with an Assistants.\
  Design it well — and every automation across your workspace becomes effortless.
</Note>

## Next steps

- Explore [Build on Phinite](/getting-started/what-you-can-build) — solution types and use cases
- Review [Assistant Components](/assistants/components)
- Configure [Triggers & Intents](/triggers-intents/overview)
- Build your first agent graph in [Graph Studio](/graph-studio/overview)
- Expose agents for external discovery in [A2A](/agent-registry/overview)