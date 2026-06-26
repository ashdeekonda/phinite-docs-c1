---
title: "Deployment & visibility"
description: "Understand test vs live deployment status and public vs organisation visibility for A2A registry builds."
icon: "sliders"
---

Every A2A registry build has **two independent settings**. They are set at different times and control different behaviour. Do not conflate them.

| Axis | Field | Set when | Controls |
| ---- | ----- | -------- | -------- |
| **Deployment status** | `test` or `live` | **Expose** creates `test`; **Push To Prod** sets `live` | Which hosted URL shape is used and which build is production for the graph |
| **Visibility** | `public` or `organization` | **Expose wizard step 3** (Agent Card) | Who may invoke the agent and who sees it in cross-org discovery |

<Note>
**Public + Live** is not one action. Choose **Public** (or **Organisation**) when you attach the Agent Card. Promote to **Live** separately from **[Agent Cards](/agent-registry/agent-cards)**.
</Note>

---

## Test vs live (deployment status)

| | **Test** | **Live** |
| --- | --- | --- |
| **Purpose** | Validate Agent Card, skills, tools, and integrations before production routing | The **one** production build per agent graph per workspace |
| **Created** | Every **Expose as External Agent** action | **Push To Prod** on a test build |
| **Hosted URL** | `{gateway}/api/v1/ai/a2a/{flowId}/{registryId}` | `{gateway}/api/v1/ai/a2a/{flowId}` |
| **How many** | Many test builds per graph | **One live** per graph per workspace; promoting demotes the previous live → test |

Test builds pin the URL to a specific registry row so you can validate that exact build. Live builds use the short path — callers route to the current live build for that graph.

See **[Endpoints & lifecycle](/agent-registry/endpoints-and-lifecycle#registry-lifecycle)** for URL patterns and the promote API.

<Info>
**A2A test/live** is separate from **[assistant builds](/builds/overview)** (Dev, UAT, Prod). Align both before you promote an agent to live — the graph that runs in-product should match the build you expose and promote.
</Info>

---

## Public vs organisation (visibility)

| | **Organisation** | **Public** |
| --- | --- | --- |
| **Purpose** | Internal agents — same org only | Callable by any client with a valid Phinite **API key** |
| **Set in UI** | Expose wizard → **Visibility & access** → **Organisation** (default in many flows) | Same step → **Public** |
| **Invoke auth** | API key org must **match** the registry row's org | Any valid API key |
| **Changed by Push To Prod?** | **No** — only deployment status updates | **No** |

At the gateway, organisation-scoped agents return an auth error when the caller's org does not match. Public agents accept any valid API key.

---

## The 2×2 matrix

Combine deployment status and visibility to understand what each build can do:

| | **Organisation** | **Public** |
| --- | --- | --- |
| **Test** | **Org test** — internal QA; test URL; visible in your org catalog; not listed for other orgs | **Public test** — callable with test URL + API key if the caller has the link; **not** in other orgs' public catalog |
| **Live** | **Org live** — production for your org; live URL; use with [Browse](/agent-registry/registry-agent-nodes) / [Discovery](/agent-registry/registry-agent-nodes) internally | **Public live** — cross-org discovery; workspace catalog with Public + Live filters; [Claude](/agent-registry/invoke-a2a-from-claude) `status=live` |

### Who sees what in the catalog

| Viewer | What appears |
| ------ | ------------ |
| **Your organisation** | Test and live builds for your org (both visibility values) |
| **Other organisations** | Only **`public` + `live`** builds |

Use **[Browse the catalog](/agent-registry/catalog)** filters (**Visibility**, **Deployed**) to confirm the state you expect.

---

## Common goals

| Goal | Visibility at expose | Promote to live? | Verify |
| ---- | -------------------- | ---------------- | ------ |
| Internal agent for your team | Organisation | Yes, when ready for production URL | Catalog: Organisation + Live; test URL first |
| Multi-agent graph calling another agent in your org | Organisation | Yes for production routing | [Browse node](/agent-registry/registry-agent-nodes) on master agent |
| Agent callable by external clients or other orgs | **Public** | **Yes** — required for cross-org catalog | Catalog: Public + Live; [Claude discovery](/agent-registry/invoke-a2a-from-claude) with `status=live` |
| Validate before any production use | Either | No — stay on test | Call test URL; check [Observability](/observability/logs) |

---

## Changing visibility after expose

**Push To Prod** does not change visibility. To update an Agent Card after registration, use the registry API (`PUT /a2a-registry/{id}` with an updated `agent_card`). Confirm whether your environment exposes a UI for this — the expose wizard is the primary place to set visibility today.

---

## Related pages

<CardGroup cols={2}>
  <Card title="End-to-end publish journey" href="/agent-registry/publish-journey" icon="route">
    Checklist from graph design through public-live verification.
  </Card>
  <Card title="Expose wizard" href="/agent-registry/expose-your-flow" icon="rocket">
    Where visibility is set; every expose starts as test.
  </Card>
  <Card title="Agent Cards & promote" href="/agent-registry/agent-cards" icon="layers">
    Push To Prod and live URL behaviour.
  </Card>
  <Card title="Endpoints & lifecycle" href="/agent-registry/endpoints-and-lifecycle" icon="plug">
    URLs, auth, and registry API reference.
  </Card>
</CardGroup>
