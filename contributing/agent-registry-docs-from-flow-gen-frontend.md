# Adding the Agent Registry (A2A) docs module — guide for contributors

This note is **not** part of the published Mintlify sidebar. Keep it in `contributing/` for anyone who maintains user docs alongside the **`flow-gen-frontend`** workspace (`phinite-fe/flow-gen-frontend`).

## Goal

Ship a cohesive **Agent Registry** section that matches what the product does today: exposing a Graph Studio flow as an **A2A** endpoint, registering it via the gateway, browsing cards in **Agent Registry**, and promoting builds to live.

## Source of truth in `flow-gen-frontend`

Use these paths when validating screenshots, UX order, API usage, or copy:

| Topic | Primary code |
| ----- | ----------- |
| “Expose as external agent” wizard (card fields, skills, visibility, auth schemes) | `src/components/headers/canvas/ExposeAsExternalAgentWizard.tsx` |
| “Expose as Agent” shortcut / modal URL patterns | `src/components/headers/canvas/BottomHeader.tsx` (`ExposeAsAgentModal`, `ExposeAsExternalAgentWizard`) |
| Workspace Agent Registry UI (tabs, list, pagination) | `src/app/[orgName]/workspace/[workspaceId]/agent-registry/page.tsx` |
| Project-scoped Agent Registry (same behaviour, different route) | `src/app/[orgName]/workspace/[workspaceId]/projects/[projectId]/agent-registry/page.tsx` |
| Redux: list / promote live / flows | `src/redux/slices/agentRegistrySlice.ts` (`GET /a2a-registry`, `PUT .../promote-live`) |
| Redux: register agent payload | `src/redux/slices/agentWizardSlice.ts` (`POST /a2a-registry`) |
| Sidebar entry + permission flag | `src/components/Layout/workspaceLayout/layout.tsx`, `src/components/Sidebar/sidebarPrimary/index.tsx` (`workspace.sidebar.agent_registry` / variants) |
| Sample card JSON shape (demo “Sample” tab) | `src/app/[orgName]/workspace/[workspaceId]/agent-registry/agents.json` |

## Gateway API surface (from the SPA)

Documentation should stay aligned with how the SPA calls the gateway (`ApiService.getExternalClient` + `config.api.gatewayUrl`):

- **GET** `/a2a-registry` — list agents (query params vary: `workspaceid`, `orgid`, `page`, `limit`, `status`, `flowid`, `flow_list`, `pagination`, `a2aregistryid`, etc.).
- **POST** `/a2a-registry?workspaceid=...` — create/update registration (wizard payload).
- **PUT** `/a2a-registry/{a2aregistryid}/promote-live` — promote to live (Builds UX).

Hosted A2A URL pattern exposed in-app (AI Core base from `NEXT_PUBLIC_AI_CORE_SERVER_URL`, default `https://ai-core-dev.phinite.ai`):

- Non-live builds often use `{base}/a2a/{flowId}/{registryId}`.
- Live routing may shorten to `{base}/a2a/{flowId}` (registry id omitted).

Confirm exact behaviour in `BottomHeader.tsx`, `ExposeAsExternalAgentWizard.tsx`, and `ModernStudio.tsx` before documenting environment-specific URLs.

## How to scaffold the Mintlify module

Phinite Docs uses **`docs.json`** (`$schema: https://mintlify.com/docs.json`). To add or extend this module:

1. **Add Markdown / MDX files** under `/agent-registry/` (paths must match **no extension** entries in `docs.json`).
2. **Register pages** under `navigation.tabs[] → Documentation → groups` (see the **Agent Registry (A2A)** group added next to Building Assistants / Graph Studio).
3. **Front matter** — each published page needs at minimum:

```yaml
---
title: "Page title"
description: "One line for SEO / cards."
---
```

4. **Cross-link** from existing Graph Studio pages (`graph-studio/publishing.md`, `graph-studio/agent-node.md`) once the UX is stable — avoid orphaned content.

## Suggested doc map (grow over time)

| Page | Audience | Notes |
| ---- | --------- | ----- |
| `agent-registry/overview` | Everyone | Concept: registry + A2A + linkage to flows/builds |
| `agent-registry/expose-your-flow` | Builders | Wizard steps; visibility; skills; auth schemes |
| `agent-registry/catalog` | Operators | Tabs: Organisation / Public / Sample; search |
| `agent-registry/endpoints-and-lifecycle` | Integrators | Test vs live, promote, endpoint URL patterns |

Replace **Sample** tab content cautiously: shipped UI uses local `agents.json` for demos; org/public tabs hit the API.

## PR checklist

- [ ] Screenshots match current **workspace** sidebar and routes (`.../agent-registry`).
- [ ] Permission name for sidebar matches IAM docs or is called out if internal-only.
- [ ] Endpoint and environment variable names reflect deployment (don’t document only `ai-core-dev` if prod differs).
- [ ] Links to external “A2A protocol” docs match whatever marketing/support approves (`BottomHeader` links out for protocol learn-more).
