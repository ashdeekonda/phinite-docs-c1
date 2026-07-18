---
title: Quickstart
description: Empty workspace to a deployable Agent Graph build.
icon: rocket
---

End-to-end path from **Workspace Home** to a deployed build using current Graph Studio labels.

<CardGroup cols={2}>
  <Card title="About Phinite" icon="book-open" href="/getting-started/about-phinite">
    Platform overview and golden path.
  </Card>
  <Card title="Graph Studio" icon="diagram-project" href="/graph-studio/overview">
    Design nodes, tools, RAG, and variables on the canvas.
  </Card>
  <Card title="Builds" icon="layer-group" href="/builds/overview">
    Freeze graph + tool versions into an immutable build.
  </Card>
  <Card title="Deploy" icon="paper-plane" type="tip" href="/agents/deploy">
    Channel, Chat API, trigger, or A2A targets.
  </Card>
</CardGroup>

## Before you begin

You should already have:

- A verified **Phinite account**
- Access to a **workspace** (created at signup)
- Permission to create Agent Graphs in that workspace

<Note>
  If you haven't signed up yet, start at [Signing Up](/setup-account/signing-up).
</Note>

## Create and design an Agent Graph

1. Open **Workspace Home**.
2. Click **New Agent Graph**.
3. Enter **Agent Graph Name** and **Description**.
4. Choose **Conversational** or **Autonomous**.
5. Click **Create Agent Graph** — Graph Studio opens on the canvas.
6. Add and connect [nodes](/graph-studio/nodes); attach [tools](/graph-studio/agent-node/tools) and [RAG](/graph-studio/agent-node/rag) as needed.
7. Click **Save** on the toolbar.

<Frame caption="New Agent Graph — choose Conversational or Autonomous">
  <img src="/images/v2/agents/01-new-agent-graph-modal.png" alt="New Agent Graph modal with type picker" />
</Frame>

<Tip>
  Use **Phinite Aura** in Graph Studio to scaffold a first draft from natural language, then refine on the canvas. See [Copilot method](/graph-studio/copilot-method).
</Tip>

## Build and assign an environment

1. Click **Build** on the Graph Studio toolbar.
2. Wait while Phinite validates the graph and packages tool versions.
3. Add a **Description** and confirm **Agent Graph** version and **Tools** (click **Publish** on any unpublished tool).
4. Click **Create Build**.
5. Assign the build to **DEV** (then **UAT** / **PROD** when ready).

<Frame caption="Build dialog — pin graph and tool versions">
  <img src="/images/v2/builds/03-build-form.png" alt="Build form with graph and tool version pins" />
</Frame>

## Deploy

1. Click **Deploy** on the Graph Studio toolbar.
2. Pick a target tab:

| Agent Graph type | Deploy tabs |
| --- | --- |
| **Conversational** | Deploy as A2A, Deploy to Channel, Deploy as Chat API |
| **Autonomous** | Deploy as API, Cron job, Deploy as A2A (coming soon) |

3. Follow the in-modal steps for your chosen target.
4. Finish channel or trigger configuration in **Integrations** if prompted.

## Test before production

1. Click **Test** in Graph Studio to open the live chat or execution panel.
2. Send sample messages or trigger payloads.
3. Review node-by-node execution in the timeline ([Observability logs](/observability/logs)).

## After first deploy

| Goal | Page |
| --- | --- |
| Channel webhooks | [Deploy to a channel](/agents/deploy-channel) |
| API / Cron | [Deploy a trigger](/agents/deploy-trigger) |
| Public A2A link | [Expose your flow](/agent-registry/expose-your-flow) |

## Troubleshooting

| Issue | Resolution |
| --- | --- |
| **Build** disabled | **Save** the graph first; publish any unpublished tools |
| **Deploy** disabled | Create at least one build |
| Test messages fail | Verify tools are published and env variables are set for DEV |
| Integration limit | Upgrade workspace plan for multi-tool support |

## Related

- [Build an agent graph](/graph-studio/overview)
- [Builds overview](/builds/overview)
- [Configure overview](/configure/overview)
- [Channels overview](/channels/overview)
