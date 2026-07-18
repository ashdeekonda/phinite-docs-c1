# Old IA coverage map (keep when skipping)

**Standing rule:** When we skip, collapse, or redirect a page, check it against the **old** Mintlify tree. Every skip must be **REDIR**, **DEFER**, **DROP**, or **DONE** (Pass 3 page exists).

## Pass 3 status (DONE pages)

| Old bucket | Pass 3 page(s) | Status |
| --- | --- | --- |
| graph-studio/nodes*, connections (collapsed) | `studio/nodes` | **DONE** |
| graph-studio/rag-management* | `rag/overview`, `rag/data-sources`, `rag/attach-to-nodes` | **DONE** |
| graph-studio/agent-node/variables, variables-panel | `studio/variables` | **DONE** |
| graph-studio/agent-node/tools | `tools/overview` + node drawer | **PARTIAL** (no separate prompt page) |
| devstudio/overview, methods | `tools/overview` | **DONE** (Open Dev Studio) |
| builds/environments | `configure/env-variables` | **DONE** |
| builds/configuration | `configure/build-export` | **DONE** |
| channels/overview, assistants/.../channels | `configure/integrations`, `agents/deploy-channel` | **DONE** (not per-vendor) |
| triggers-intents/overview | `configure/integrations`, `agents/deploy-trigger` | **DONE** |
| agent-registry/overview, catalog | `a2a/registry` | **DONE** |
| agent-registry/agent-cards, expose step 3 | `a2a/agent-card-identity` | **DONE** |
| agent-registry/registry-agent-nodes | `a2a/discovery` | **DONE** |
| agent-registry/endpoints-and-lifecycle | `a2a/endpoints` | **DONE** |
| BYOK / model keys | `workspace/models` | **DONE** |
| assistants/components (config map) | `configure/overview` | **DONE** |

## Still DEFER (not Pass 3)

| Old bucket | Count | Notes |
| --- | --- | --- |
| setup-account / workspaces | 5 | Sign-up, create workspace |
| graph-studio deep (copilot, connections, publishing) | ~15 | REDIR → nearest Design/Ship page |
| assistants/intents* | ~5 | REDIR → deploy-trigger; product TBD |
| integrations-hub per-vendor | 74 | REDIR → configure/integrations |
| observability | 11 | REDIR → what-is-phinite |
| user-management | 9 | Out of scope (not Agent Card identity) |
| reference/faqs, api, shortcuts | 4 | DEFER Pass 4 |
| support | 5 | DEFER Pass 4 |
| agent-registry/invoke-a2a-from-claude | 1 | REDIR → a2a/registry; full page DEFER |

## New spine (live nav)

See [`docs.json`](../../docs.json): Start → Design in Studio → Configure → Ship → A2A → Reference (~34 pages).

## Product DROPs (intentional)

- **Assistant** as top object → **Agent Graph**
- Email as create-type (filter chip may linger)
- Nav label **DevStudio** → **Tools** + Open Dev Studio
