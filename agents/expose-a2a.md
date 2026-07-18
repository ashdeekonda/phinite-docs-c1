---
title: Expose as A2A
description: Quick reference — publish an Agent Card and hosted A2A URL from an Agent Build.
---

**Deploy as A2A** exposes an **Agent Build** over the Agent-to-Agent protocol with an **Agent Card** — the agent's public identity for catalog search and external callers.

<Note>
  Full wizard walkthrough, Agent Card fields, and promotion: **[Expose your Agent Graph as an A2A agent](/agent-registry/expose-your-flow)**.
</Note>

## Golden path

1. **Save** the Agent Graph and create an **Agent Build** ([Builds overview](/builds/overview)).
2. In Studio, click **Deploy** → **Deploy as A2A** (or expose from **Agent Builds**).
3. **Agent Build Config** — confirm graph and tool versions; publish tools if needed.
4. **Additional Config** — optional [export tools/env/MCP](/configure/build-export) into the version.
5. **Agent Card** — configure identity, skills, tags, and visibility ([Agent Cards](/agent-registry/agent-cards)).
6. Submit — creates a **TEST** Agent Card version.
7. Review in Studio → **Agent Cards** and workspace [Agent Registry catalog](/agent-registry/catalog).
8. **Push To Prod** when ready → **LIVE** [hosted URL](/agent-registry/endpoints-and-lifecycle).

<Frame caption="Studio Agent Cards sidebar — TEST and LIVE versions per graph">
  <img src="/images/v2/a2a/01-agent-cards-sidebar.png" alt="Agent Cards sidebar in Graph Studio" />
</Frame>

<Tip>
  One **LIVE** version per Agent Graph per workspace. Promoting demotes the previous LIVE row to TEST.
</Tip>

## Agent Registry tab

<CardGroup cols={2}>
  <Card title="Expose your flow" icon="rocket" href="/agent-registry/expose-your-flow">
    Step-by-step Expose wizard.
  </Card>
  <Card title="Agent Cards" icon="id-card" href="/agent-registry/agent-cards">
    Compare builds and Push To Prod.
  </Card>
  <Card title="Endpoints & lifecycle" icon="plug" href="/agent-registry/endpoints-and-lifecycle">
    TEST vs LIVE URL patterns and auth.
  </Card>
  <Card title="Browse the catalog" icon="layout-grid" href="/agent-registry/catalog">
    Workspace Agent Registry search and filters.
  </Card>
</CardGroup>

## Related

- [Deploy](/agents/deploy)
- [Build export](/configure/build-export)
- [Agent Registry overview](/agent-registry/overview)
