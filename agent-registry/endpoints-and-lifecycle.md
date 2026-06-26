---
title: "A2A endpoints & lifecycle"
description: "Hosted URL patterns, test vs live builds, promotion, authentication, and registry API endpoints."
---

For the **test/live × public/org** model and catalog rules, see **[Deployment & visibility](/agent-registry/deployment-and-visibility)**.

## Hosted A2A URLs

External callers reach registered agents through the **API gateway** AI-core lane. The canonical invoke path uses the **registry ID**:

```
POST /api/v1/ai/a2a/agents/{registryId}
GET  /api/v1/ai/a2a/agents/{registryId}/.well-known/agent-card.json
```

The frontend also surfaces legacy URL shapes with `{flowId}` for some live/test builds (`buildA2aUrl` in the product):

| Deployment status | URL pattern | Example shape |
| ----------------- | ----------- | ------------- |
| **Live** | `{gateway}/api/v1/ai/a2a/{flowId}` | Production routing; registry ID omitted |
| **Test** | `{gateway}/api/v1/ai/a2a/{flowId}/{registryId}` | Validation build tied to a specific registry row |

```text
# Preferred (registry ID)
https://app.phinite.ai/api/v1/ai/a2a/agents/{registryId}

# Legacy shapes (still shown in some UI copy)
https://app-dev.phinite.ai/api/v1/ai/a2a/{flowId}
https://app-dev.phinite.ai/api/v1/ai/a2a/{flowId}/{a2aregistryid}
```

Replace the host with your environment’s gateway base (`NEXT_PUBLIC_BACKEND_SERVER_URL` → `/api/v1`, then append `/ai` for the AI-core lane). Graph Studio and Agent Registry copy the authoritative string for your tenant—always use the value shown in the UI rather than constructing URLs manually.

For local development with the dev API proxy, the same paths may appear under `http://localhost:3000/api/v1/ai/a2a/...`.

## Registry lifecycle

Each expose action creates an **A2A registry** row with deployment status **`test`** by default.

| Status | Meaning | Hosted URL |
| ------ | ------- | ---------- |
| **`test`** | Internal validation before broad discovery | Includes `{registryId}` in path |
| **`live`** | Production build for the agent graph | Short path with `{flowId}` only |

**One live build per agent graph per workspace.** Promoting a build to live demotes any previous live row for the same `flowid` back to **`test`**.

### Promote to live

From **[Agent Cards](/agent-registry/agent-cards)**, select a test build and use **Push To Prod** (promote flow). The app calls:

```
PUT /api/v1/a2a-registry/{a2aregistryid}/promote-live
```

No request body is required. The response is the updated registry document with `status: "live"`.

## Visibility and authentication

Each Agent Card declares **visibility** (set in the [expose wizard](/agent-registry/expose-your-flow), unchanged by promote). Cross-org catalog listing requires **`public` + `live`** — see **[Deployment & visibility](/agent-registry/deployment-and-visibility#the-2×2-matrix)**.

| Visibility | UI label | Invoke behaviour (high level) |
| ---------- | -------- | ------------------------------ |
| **`public`** | Public | Callable by any client presenting a valid Phinite **API key** |
| **`organization`** | Organisation | Callable only when the API key belongs to the **same organisation** as the registry row |

At runtime, the gateway **`A2ARegistryAccess`** middleware validates visibility when agents are invoked (for example `POST /api/v1/ai/a2a/agents/{registryId}`). Organisation-scoped agents return an auth error if the caller’s org does not match.

**Auth scheme in the product:** callers use your organisation’s **API key** (JWT) in the `X-API-Key` header unless your deployment configures additional schemes.

## External clients (Claude Connector)

End users can call registry agents from **Claude** via the [Phinite Connector](/agent-registry/invoke-a2a-from-claude) without constructing A2A URLs manually.

| Layer | Behaviour |
| ----- | --------- |
| **Connector auth** | User signs in to Phinite (Google or email) when connecting the plugin in Claude |
| **Discovery** | `discover_agents` / `list_agents` query the same registry metadata as the workspace catalog |
| **Invocation** | `call_agent` maps to A2A `SendMessage` on `POST /api/v1/ai/a2a/agents/{registryId}` |
| **Multi-turn** | Pass `task_id` from a prior response to continue the same A2A task |
| **Tool credentials** | If the build requires integrations and no valid config exists, the runtime returns **`TASK_STATE_AUTH_REQUIRED`** with a link to **`/public/agent-config`** |

Full install steps, tool parameters, and credential lifecycle: **[Invoke A2A agents from Claude](/agent-registry/invoke-a2a-from-claude)**.

## Agent Card contract for integrators

Integrators and A2A-compatible clients should consume:

- **Agent name and description** from the Agent Card
- **Skills** — each skill lists supported **input modes** and **output modes** (MIME types)
- **Discoverability tags** — for search and Discovery matching
- **Hosted URL** — test vs live pattern above

See the **[A2A glossary](/agent-registry/glossary)** for supported MIME types.

Official protocol details: **[A2A protocol specification](https://a2a-protocol.org/latest/specification/)**.

## Registry management API

All routes require gateway authentication (session cookie or Bearer token / API key). Base path: **`/api/v1/a2a-registry`**.

| Method | Path | Purpose |
| ------ | ---- | ------- |
| `GET` | `/a2a-registry` | List registry rows (`workspaceid` required; optional `orgid`, `status`, `visibility`, `flowid`, filters) |
| `GET` | `/a2a-registry/{a2aregistryid}` | Get one row (`?flow=true` includes decrypted flow payload) |
| `POST` | `/a2a-registry?workspaceid=...` | Create registration (Expose wizard) |
| `PUT` | `/a2a-registry/{a2aregistryid}` | Update registration |
| `PUT` | `/a2a-registry/{a2aregistryid}/promote-live` | Promote to live |
| `DELETE` | `/a2a-registry/{a2aregistryid}` | Delete registration |

**Permissions (api-server):** `assistants.flows:read|create|update|delete` depending on operation.

### Useful list query parameters

| Parameter | Values | Use |
| --------- | ------ | --- |
| `workspaceid` | string | **Required** — scopes to workspace |
| `orgid` | string | Organisation filter (must match caller’s org) |
| `status` | `test`, `live` | Deployment filter |
| `visibility` | `public`, `organization` | Top-level visibility filter |
| `flowid` | string | All builds for one agent graph |
| `flow_list=true` | boolean | Returns distinct flows only (Agent Cards dropdown) |
| `pagination` | `true` / `false` | Paginated vs full list |

## Related pages

<CardGroup cols={2}>
<Card title="Invoke from Claude" href="/agent-registry/invoke-a2a-from-claude" icon="plug">
Phinite Connector install, tools, and credential setup.
</Card>
<Card title="Expose an agent" href="/agent-registry/expose-your-flow" icon="rocket">
Create a test build and Agent Card.
</Card>
<Card title="Agent Cards" href="/agent-registry/agent-cards" icon="layers">
Promote test builds to live.
</Card>
</CardGroup>
