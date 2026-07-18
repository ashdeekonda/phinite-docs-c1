# Old IA coverage map (keep when skipping)

**Standing rule:** When we skip, collapse, or redirect a page, check it against the **old** Mintlify tree (Assistants → Graph Studio → DevStudio → Triggers → Builds → Registry → Integrations Hub → Observability → User Mgmt). Every skip must be intentional: **REDIR**, **DEFER** (Pass N), or **DROP** (product gone) — never silent.

Pass 1–2 spine (~12 pages) covers the new agent-first journey only. **~218** legacy `.md` files remain on disk, unreferenced by the new `docs.json` nav.

## New spine (live)

| New page | Absorbs (old concept) |
| --- | --- |
| `what-is-phinite` | getting-started/about, what-you-can-build |
| `quickstart` | getting-started/quickstart |
| `agents/overview` | assistants/types, conversational, autonomous |
| `agents/build-graph` | graph-studio overview + interface + nodes (collapsed) |
| `tools/overview` | devstudio overview (Open Dev Studio) |
| `agents/builds` | builds/overview, assistants/.../builds, publishing |
| `agents/environments` | builds/environments, assistants/.../environments |
| `agents/deploy` | deploy branching (new) |
| `agents/deploy-channel` | channels/overview, assistants/.../channels |
| `agents/deploy-trigger` | triggers-intents/overview (+ triggers) |
| `agents/expose-a2a` | agent-registry overview, expose, agent-cards |
| `reference/glossary-v2` | reference/glossary |

## Gap inventory by old bucket

| Old bucket | On disk | Status | Next action |
| --- | --- | --- | --- |
| getting-started | 3 | mostly REDIR | — |
| setup-account / workspaces | 5 | **SKIP** | DEFER: sign-up, create workspace |
| assistants | 14 | partial REDIR | DEFER or DROP: intents / intents-email (product?) |
| graph-studio | 31 | mostly **SKIP** | DEFER: nodes, RAG, variables, connections (deep how-tos) |
| devstudio | 20 | thin REDIR | DEFER: custom tools, prebuilt, versioning, testing |
| builds | 5 | partial REDIR | DEFER: lifecycle, configuration |
| channels | 9 | thin REDIR | DEFER: per-channel (WhatsApp, Slack, …) |
| triggers-intents | 15 | thin REDIR | DEFER: intents, cron/api detail, prompt training |
| agent-registry | 8 | partial REDIR | DEFER: catalog, endpoints, Claude connector, registry nodes |
| integrations-hub | 74 | **SKIP** all | DEFER: thin catalog or generate later |
| observability | 11 | **SKIP** | DEFER: logs, metrics, billing |
| user-management | 9 | **SKIP** | DEFER: roles, invites, access |
| reference | 6 | thin REDIR | DEFER: FAQ, API, shortcuts, release notes |
| support | 5 | **SKIP** | DEFER: errors, chatbot knowledge rack |

## When skipping, do this

1. Name the old path(s) in the PR / manifest.
2. Classify: **REDIR** (SEO) / **DEFER** (still true, not written) / **DROP** (product removed — e.g. Assistant as top object).
3. Prefer a redirect to the nearest new spine page over a 404.
4. Do not delete legacy files until DEFER backlog is empty or explicitly archived.

## Product DROPs (intentional)

- **Assistant** as top object → **Agent Graph**
- Separate “Building Assistants” chapter → Agents spine
- Nav label **DevStudio** → **Tools** + Open Dev Studio
- Email as create-type (filter chip may linger; create picker is Conversational | Autonomous only)
