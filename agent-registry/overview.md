---
title: "Agent Registry overview"
description: "Discover how Phinite publishes flows as discoverable agents and connects them via the Agent-to-Agent (A2A) protocol."
---

## What the Agent Registry is

The **Agent Registry** is the catalog inside your workspace where published agent registrations appear. Each entry corresponds to an **agent card** backed by an **agent graph** (flow) build. Other systems and compatible agents can call your agent using its **A2A** endpoint.

You typically:

1. **Design** your agent logic in Graph Studio (**Agent** nodes on the canvas).
2. **Expose** that flow through **Expose as external agent** (from the Studio header tooling) after you have a suitable build.
3. **Browse** and manage registrations from **Agent Registry** in the workspace sidebar—filtering organisation vs catalogue entries depending on deployment.
4. **Promote** a registration to **live** when your team is ready (from Builds / registry flows wired to `/a2a-registry/.../promote-live` in the application).

## How this relates to Graph Studio

- The **workflow** defines behaviour; **exposing** it creates or updates registry metadata so callers get a stable **skills** listing, visibility, authentication expectations, and the **hosted A2A URL**.
- Detailed node configuration stays in **[Agent Node anatomy](/graph-studio/agent-node)** and **[Publishing](/graph-studio/publishing)**—this module focuses on **registry** and **A2A consumption**.

## Next steps

<CardGroup cols={2}>
<Card title="Expose a flow as an agent" href="/agent-registry/expose-your-flow" icon="rocket">
Walk through exposing a flow and filling out the agent card.
</Card>
<Card title="Browse the catalog" href="/agent-registry/catalog" icon="layout-grid">
Use organisation and public catalogue tabs and locate endpoints.
</Card>
<Card title="Endpoints & lifecycle" href="/agent-registry/endpoints-and-lifecycle" icon="plug">
Understand test vs live URLs and promotion.
</Card>
</CardGroup>
