---
title: "Triggers & Intents"
description: "How workflows start — intents for conversational and email assistants, triggers for autonomous assistants."
icon: "bullseye"
---

Every assistant needs an **entry point** — the signal that starts an agent graph. Which entry point you configure depends on your [solution type](/getting-started/what-you-can-build):

| Assistant type | Sidebar item | Entry mechanism | Purpose |
| --- | --- | --- | --- |
| **Conversational** | Intents | Natural language detection | Route chat and voice messages to the right graph |
| **Email** | Intents | Email classification + filters | Triage inbound mail and start processing graphs |
| **Autonomous** | Triggers | API, schedule, or integration event | Run background automation without user interaction |

<Note>
  In the product, **Intents** and **Triggers** appear under **Build** in the assistant sidebar. This section is the canonical reference for configuring them — you do not need a separate guide under Assistant Components.
</Note>

---

## Intents

Intents capture what a user (or email sender) wants and link that signal to an agent graph.

<CardGroup cols={2}>
  <Card title="Conversational intents" icon="comments" href="/triggers-intents/intents">
    Chat and voice routing with training phrases and testing.
  </Card>
  <Card title="Email intents" icon="envelope" href="/triggers-intents/intents-email">
    Inbox filters, funnel configuration, and mail classification.
  </Card>
  <Card title="Prompt training" icon="wand-magic-sparkles" href="/triggers-intents/prompt-training">
    Improve recognition with better training data.
  </Card>
  <Card title="Intent as API" icon="plug" href="/triggers-intents/intent-as-api">
    Start a conversation programmatically in a selected channel.
  </Card>
</CardGroup>

---

## Triggers

Triggers start agent graphs for autonomous assistants — without a user typing a message.

<CardGroup cols={2}>
  <Card title="Triggers overview" icon="play" href="/triggers-intents/triggers">
    API, background task, and scheduler trigger types.
  </Card>
  <Card title="Trigger APIs" icon="code" href="/triggers-intents/triggers/api-guide">
    HTTP endpoints, authentication, and payloads.
  </Card>
  <Card title="Event triggers" icon="calendar" href="/triggers-intents/event-triggers">
    Cron, email events, and integration funnels.
  </Card>
  <Card title="Mapping" icon="diagram-project" href="/triggers-intents/mapping">
    Connect entry points to agent graphs.
  </Card>
</CardGroup>

---

## Quick reference

| I want to… | Go to |
| --- | --- |
| Route a chat message to a graph | [Conversational intents](/triggers-intents/intents) |
| Classify and process inbound email | [Email intents](/triggers-intents/intents-email) |
| Start a graph from a webhook or API | [Trigger APIs](/triggers-intents/triggers/api-guide) |
| Run a graph on a schedule | [Triggers](/triggers-intents/triggers) → Scheduler |
| Test intent recognition before deploy | [Testing intents](/triggers-intents/testing-intents) |
