# Agent Registry (A2A) documentation — contributor guide

This note is **not** part of the published Mintlify sidebar. Use it when maintaining user docs alongside **`flow-gen-frontend`**, **`api-server-2`**, and **`api-gateway`**.

## Goal

Keep the **Agent Registry (A2A)** module aligned with the product: expose wizard, workspace catalog, Browse/Discovery agent nodes, Agent Cards builds, hosted URLs, promote-live lifecycle, and Claude connector consumption.

## Published doc map

Registered in **`docs.json`** under **7. Agent Registry (A2A)**:

| Page | Path | Audience |
| ---- | ---- | -------- |
| Overview | `agent-registry/overview` | Concepts, workflow, terminology (incl. former glossary) |
| Publish and endpoints | `agent-registry/publish` | Expose wizard, Agent Cards, hosted URLs |
| Compose on canvas | `agent-registry/compose` | Registry agent nodes, catalog |
| Invoke from Claude | `agent-registry/invoke-a2a-from-claude` | Phinite Connector: install, tools, credentials |

Legacy paths (`expose-your-flow`, `agent-cards`, `catalog`, `glossary`, etc.) redirect to anchors on the consolidated pages above.

Cross-links: **`graph-studio/publishing.md`**, **`graph-studio/agent-node.md`**, **`index.md`**.

## Source of truth in `flow-gen-frontend`

| Topic | Primary code |
| ----- | ----------- |
| Expose wizard (3 steps, Agent Card fields) | `src/components/headers/canvas/ExposeAsExternalAgentWizard.tsx` |
| Expose modal + Configure Agent entry | `src/components/headers/canvas/BottomHeader.tsx` |
| Browse / Discovery panel | `src/components/headers/canvas/BrowseAgentsModal.tsx` |
| Studio wiring (discovery limits) | `src/app/.../studio/components/ModernStudio.tsx` |
| Workspace Agent Registry UI | `src/app/[orgName]/workspace/[workspaceId]/agent-registry/page.tsx` |
| Agent Cards (builds, promote) | `src/app/.../projects/[projectId]/agent-cards/page.tsx` |
| Agent detail / build picker | `src/components/headers/canvas/AgentLoadModal.tsx` |
| Filters sidebar | `src/components/ui/AgentFiltersSidebar.tsx` |
| Redux: list / promote / fetch by id | `src/redux/slices/agentRegistrySlice.ts` |
| Redux: register agent | `src/redux/slices/agentWizardSlice.ts` |
| A2A URL builders | `src/utils/gatewayUrls.ts` (`buildA2aUrl`) |
| Dev/local feature gate | `src/utils/config.ts` (`isLocalOrDevEnv`) |
| Sidebar + permission | `src/components/Layout/workspaceLayout/layout.tsx`, `workspace.sidebar.agent_registry` |

## Backend and gateway

| Topic | Primary code |
| ----- | ----------- |
| Registry CRUD + list filters | `api-server-2/src/services/orgLevel/workspaceLevel/a2aRegistry.service.ts` |
| Model (`status`, `visibility`) | `api-server-2/src/models/Assistant/A2A.ts` |
| Promote live | `PUT /a2a-registry/:id/promote-live` |
| Gateway routes | `api-gateway/internal/routes/api_server_routes.go` |
| Runtime visibility | `api-gateway/internal/middleware/a2a_registry.go` |
| Public agent config | `flow-gen-frontend/src/app/public/agent-config/page.tsx`, `publicAgentConfigService.ts` |
| A2A auth-required state | `api-gateway/internal/middleware/a2a/registry.go` (`TASK_STATE_AUTH_REQUIRED`) |

### Claude Connector (external)

| Topic | Primary source |
| ----- | -------------- |
| Plugin marketplace & tools | [phinite-plugins](https://github.com/Auto-AI-Labs/phinite-plugins) |
| Consumer user doc | `docs/agent-registry/invoke-a2a-from-claude.md` |
| A2A + MCP packaging plan | `flow-gen-frontend/docs/publish-a2a-as-mcp-server.md` |
| Public config auth design | `flow-gen-frontend/docs/public-agent-config-authorization.md` |

## Gateway API surface (SPA)

- **GET** `/api/v1/a2a-registry` — list (`workspaceid` required; optional `orgid`, `status`, `visibility`, `flowid`, `flow_list`, etc.)
- **POST** `/api/v1/a2a-registry?workspaceid=...` — create (Expose wizard)
- **PUT** `/api/v1/a2a-registry/{a2aregistryid}/promote-live` — promote to live
- **GET/PUT/DELETE** `/api/v1/a2a-registry/{a2aregistryid}` — single row

**Hosted URLs (gateway AI lane):**

- **Live:** `{gateway}/api/v1/ai/a2a/{flowId}`
- **Test:** `{gateway}/api/v1/ai/a2a/{flowId}/{registryId}`

Do **not** document legacy direct AI-core hostnames as the primary contract—use gateway paths from `buildA2aUrl`.

## Screenshot checklist

Place PNGs in **`docs/images/agent-registry/`** (see `images/agent-registry/README.md`).

### Environment

- **App env:** `NEXT_PUBLIC_APP_ENV=local` or `dev` (or `NODE_ENV=development`)
- **Role:** Developer or higher; **`workspace.sidebar.agent_registry`** enabled
- **Backend:** Gateway + api-server with registry data (at least one exposed test agent)

### URLs to capture

Replace `{org}`, `{workspaceId}`, `{projectId}` with your tenant:

```
http://localhost:3000/{org}/workspace/{workspaceId}/agent-registry
http://localhost:3000/{org}/workspace/{workspaceId}/projects/{projectId}/studio
http://localhost:3000/{org}/workspace/{workspaceId}/projects/{projectId}/agent-cards
```

**Configure Agent** and **Expose as External Agent** appear only when dev/local gating is active.

### Required shots

- [ ] `overview-hero.png` — Agent Registry catalog
- [ ] `expose-modal.png` — Expose as Agent modal
- [ ] `wizard-step1-build-config.png` — Step 1
- [ ] `wizard-step3-agent-card.png` — Step 3 Agent Card
- [ ] `expose-success.png` — Success + registry ID
- [ ] `registry-search.png` — Search + main panel
- [ ] `registry-filters.png` — Filter sidebar
- [ ] `registry-detail.png` — Agent detail
- [ ] `agent-node-browse-discovery-toggle.png` — Browse | Discovery
- [ ] `discovery-filters.png` — Discovery filters
- [ ] `discovery-config.png` — Discovery API key config
- [ ] `agent-cards-builds.png` — Agent Cards table

## Accuracy checklist (before merge)

- [ ] Wizard step titles: **Agent Build Config**, **Additional Config**, **Configure the Agent card**
- [ ] Final CTA: **Attach Agent Card** (not "Register" or generic "Submit")
- [ ] No **Sample tab** references (removed from UI)
- [ ] **One Discovery node per master agent** documented
- [ ] URL patterns match `buildA2aUrl` / gateway `/api/v1/ai/a2a/...`
- [ ] Permission: `workspace.sidebar.agent_registry`
- [ ] British **Organisation** spelling where quoting UI
- [ ] Note **Agent Block** vs **Agent Node** where UI still says Block
- [ ] Public catalog: honest note on `status=live` vs `visibility=public` filtering
- [ ] External A2A link: https://a2a-protocol.org/latest/specification/
- [ ] Placeholder images exist or README lists pending captures

## Mintlify scaffolding

1. Add or edit Markdown under **`docs/agent-registry/`** (paths match **`docs.json`** entries without extension).
2. Front matter: `title`, `description` (required).
3. Use `<CardGroup>`, `<Steps>`, `<Warning>` where helpful—match existing docs style.
4. Run **`mint dev`** from **`docs/`** to preview.

## Out of scope for user docs

- Backend visibility filter redesign
- Production rollout dates for registry gating
- Billing/session limits for A2A invokes (see observability/billing docs)
