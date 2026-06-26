---
title: "Phinite Documentation"
description: "Build assistants, agent graphs, tools, and integrations with enterprise controls."
sidebarTitle: "Home"
---

## Start here

<CardGroup cols={3}>
  <Card title="Welcome" icon="sparkles" href="/getting-started/about-phinite">About Phinite and this manual</Card>
  <Card title="Quickstart" icon="rocket" href="/getting-started/quickstart">Your first assistant and agent graph</Card>
  <Card title="Workspace Overview" icon="grid" href="/workspaces/workspace-overview">Org → workspace → assistant</Card>
  <Card title="What you can build" icon="layer-group" href="/getting-started/what-you-can-build">Solution types and use-case patterns</Card>
  <Card title="User Management" icon="users" href="/user-management/user-management">Invite users and manage access</Card>
  <Card title="User Roles" icon="id-badge" href="/user-management/user-roles">Admin, Developer, QA capabilities</Card>
  <Card title="Invite Users" icon="envelope" href="/user-management/inviting-users">Add teammates and assign roles</Card>
  <Card title="Shortcuts" icon="bolt" href="/reference/shortcuts">Productivity shortcuts</Card>
  <Card title="FAQs" icon="circle-question" href="/reference/faqs">Common questions</Card>
</CardGroup>

## Build assistants

<CardGroup cols={3}>
  <Card title="Build on Phinite" icon="layer-group" href="/getting-started/what-you-can-build">Solution types, use cases, and patterns</Card>
  <Card title="Assistant Overview" icon="bot" href="/assistants/overview">Architecture, sidebar, and creation steps</Card>
  <Card title="Components" icon="puzzle-piece" href="/assistants/components">Agent graphs, tools, builds, channels</Card>
  <Card title="Conversational" icon="comments" href="/assistants/conversational">Chat and voice assistants</Card>
  <Card title="Email" icon="envelope" href="/assistants/email">Inbox automation</Card>
  <Card title="Autonomous" icon="robot" href="/assistants/autonomous">Background jobs and APIs</Card>
  <Card title="Agent Graphs" icon="diagram-project" href="/assistants/components/flows">How graphs power assistants</Card>
  <Card title="Tools" icon="wrench" href="/assistants/components/tools">Extend assistants with actions</Card>
  <Card title="Channels" icon="comments" href="/assistants/components/channels">Where assistants run</Card>
</CardGroup>

## Graph Studio

<CardGroup cols={3}>
  <Card title="Overview" icon="diagram-project" href="/graph-studio/overview">Visual agent graph builder</Card>
  <Card title="Methods" icon="magic" href="/graph-studio/methods">Phinite Aura vs manual</Card>
  <Card title="Nodes" icon="cubes" href="/graph-studio/nodes">Start, agents, tool, end</Card>
  <Card title="Connections" icon="share-nodes" href="/graph-studio/connections">Edges, handles, conditionals</Card>
  <Card title="RAG & Collections" icon="book" href="/graph-studio/rag-management">Collections and retrieval</Card>
  <Card title="Publishing" icon="upload" href="/graph-studio/publishing">Save as Version and release builds</Card>
</CardGroup>

## A2A (Agent-to-Agent)

<CardGroup cols={3}>
  <Card title="A2A overview" icon="share-nodes" href="/agent-registry/overview">Publish, discover, and compose agents</Card>
  <Card title="Publish an agent" icon="rocket" href="/agent-registry/expose-your-flow">Expose wizard & Agent Card</Card>
  <Card title="Agent Cards & builds" icon="layers" href="/agent-registry/agent-cards">Test and live deployments</Card>
  <Card title="Browse the catalog" icon="layout-grid" href="/agent-registry/catalog">Search workspace agents</Card>
  <Card title="Compose on canvas" icon="diagram-project" href="/agent-registry/registry-agent-nodes">Browse & Discovery nodes</Card>
  <Card title="Invoke from Claude" icon="plug" href="/agent-registry/invoke-a2a-from-claude">Phinite Connector</Card>
  <Card title="Endpoints & lifecycle" icon="link" href="/agent-registry/endpoints-and-lifecycle">URLs, auth, promote to live</Card>
  <Card title="A2A glossary" icon="book-open" href="/agent-registry/glossary">Terms and MIME modes</Card>
</CardGroup>

## DevStudio (Tool Builder)

<CardGroup cols={3}>
  <Card title="Overview" icon="screwdriver-wrench" href="/devstudio/overview">Build and test tools</Card>
  <Card title="Methods" icon="lightbulb" href="/devstudio/methods">Phinite Aura and manual coding</Card>
  <Card title="Tool Types" icon="gears" href="/devstudio/types">Custom, system, and structure tools</Card>
  <Card title="Predefined tools" icon="plug" href="/integrations-hub/predefined-tools/workflow">Connect via Integrations</Card>
  <Card title="Versioning" icon="code-branch" href="/devstudio/versioning">Save as Version</Card>
  <Card title="Testing Tools" icon="flask" href="/devstudio/testing-tools">Run and validate tools</Card>
</CardGroup>

## Triggers & Intents

<CardGroup cols={3}>
  <Card title="Overview" icon="bullseye" href="/triggers-intents/overview">How interactions start</Card>
  <Card title="Intents" icon="comment-dots" href="/triggers-intents/intents">Conversational routing</Card>
  <Card title="Email intents" icon="envelope" href="/triggers-intents/intents-email">Inbox classification</Card>
  <Card title="Triggers" icon="play" href="/triggers-intents/triggers">Autonomous entry points</Card>
  <Card title="Trigger APIs" icon="code" href="/triggers-intents/triggers/api-guide">HTTP trigger endpoints</Card>
  <Card title="Testing Intents" icon="vial" href="/triggers-intents/testing-intents">Validate recognition</Card>
</CardGroup>

## Builds & Environments

<CardGroup cols={3}>
  <Card title="Overview" icon="server" href="/builds/overview">Release builds and deploy</Card>
  <Card title="Lifecycle" icon="recycle" href="/builds/lifecycle">Draft to deployed</Card>
  <Card title="Configuration" icon="sliders" href="/builds/configuration">Build settings</Card>
  <Card title="Environments" icon="diagram-project" href="/builds/environments">Dev, UAT, Prod</Card>
  <Card title="Env. variables" icon="key" href="/assistants/components/environments">Per-assistant variables</Card>
</CardGroup>

## Channels & Integrations

<CardGroup cols={3}>
  <Card title="Channels overview" icon="comments" href="/integrations-hub/channels/overview">Messaging and voice channels</Card>
  <Card title="Integrations" icon="plug" href="/integrations-hub/overview">Predefined tools catalog</Card>
  <Card title="Webchat" icon="message" href="/integrations-hub/channels/webchat">Embed chat on your site</Card>
  <Card title="WhatsApp" icon="whatsapp" href="/integrations-hub/channels/whatsapp">WhatsApp channel</Card>
  <Card title="Slack/Teams" icon="hashtag" href="/integrations-hub/channels/slack-teams">Slack or Teams</Card>
  <Card title="Email" icon="envelope" href="/integrations-hub/channels/email">Email channel</Card>
</CardGroup>

## Observability & Billing

<CardGroup cols={3}>
  <Card title="Overview" icon="chart-line" href="/observability/overview">Sessions and usage</Card>
  <Card title="Usage Metrics" icon="chart-bar" href="/observability/usage-metrics">Tokens, telephony, Aura</Card>
  <Card title="Session Logs" icon="scroll" href="/observability/logs">Timeline, decisions, variables</Card>
  <Card title="Filtering" icon="filter" href="/observability/filtering">Slice and search sessions</Card>
  <Card title="Billing & Usage" icon="receipt" href="/observability/billing">Plans and invoices</Card>
</CardGroup>

## Reference & Support

<CardGroup cols={3}>
  <Card title="AI Assistant (MCP)" icon="robot" href="/reference/ai-assistant">Connect docs to Cursor or Claude</Card>
  <Card title="API Reference" icon="terminal" href="/reference/api">Triggers, A2A, and platform APIs</Card>
  <Card title="Glossary" icon="book-open" href="/reference/glossary">Key terms</Card>
  <Card title="Release Notes" icon="clipboard-list" href="/reference/release-notes">What's new</Card>
  <Card title="Error Codes" icon="triangle-exclamation" href="/support/error-codes">Common errors</Card>
  <Card title="Contact Support" icon="life-ring" href="/support/contact">Get help</Card>
</CardGroup>
