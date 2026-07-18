---
title: Expose as A2A
description: Publish an Agent Card — test version, then prod public A2A link.
---

**Deploy as A2A** exposes a **Build** over the Agent-to-Agent protocol with an **Agent Card** (the agent's public identity).

## Path

1. **Save** the graph and create a **Build** ([Builds](/agents/builds)).
2. In Studio, click **Deploy** → **Deploy as A2A** (or expose from **Agent Builds**).
3. Step 1 — confirm graph and tool versions; publish tools if needed.
4. Step 2 — optional [export tools/env/MCP](/configure/build-export) into the version.
5. Step 3 — configure [Agent Card identity](/a2a/agent-card-identity) (skills, tags, visibility).
6. Submit — creates a **TEST** Agent Card version.
7. Review in Studio → **Agent Cards** and workspace [Agent Registry](/a2a/registry).
8. **Push To Prod** when ready → **LIVE** [hosted URL](/a2a/endpoints).

![Agent Cards](/images/v2/a2a/01-agent-cards-sidebar.png)

## Notes

- Conversational **Deploy as A2A** is available today.
- Autonomous **Deploy as A2A** may show as coming soon in Deploy.
- One **LIVE** version per Agent Graph per workspace; promote demotes the previous LIVE to TEST.

## Related

- [Agent Card identity](/a2a/agent-card-identity)
- [A2A endpoints](/a2a/endpoints)
- [Deploy](/agents/deploy)
- [Build export](/configure/build-export)
