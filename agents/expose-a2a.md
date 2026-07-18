---
title: Expose as A2A
description: Publish an Agent Card — test version, then prod public A2A link.
---

**Deploy as A2A** exposes a build over the Agent-to-Agent protocol with an **Agent Card**.

## Path

1. Create a **Build** of the agent graph.
2. In Studio, **Deploy** → **Deploy as A2A** (or use the expose/build wizard from Agent Builds).
3. Configure the **Agent Card** (name, description, skills, visibility).
4. Registration creates a **test** Agent Card version.
5. Review under Studio → **Agent Cards** and workspace **Agent Registry**.
6. **Push to Prod** when ready — prod is the public/callable A2A URL for that graph.

![Agent Cards](/images/v2/a2a/01-agent-cards-sidebar.png)

## Notes

- Conversational A2A is available in Deploy.
- Autonomous **Deploy as A2A** may show as coming soon.
- One live/prod card per graph per workspace is the usual promote rule.

## Related

- [Deploy](/agents/deploy)
- [Builds](/agents/builds)
- [Glossary](/reference/glossary-v2)
