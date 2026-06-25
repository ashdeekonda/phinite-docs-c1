# Phinite Docs — information architecture

Contributor reference for navigation and page structure. Not published in the Mintlify sidebar.

## Design principles

### Sections over pages

| Prefer | Avoid |
|--------|-------|
| One guide with 4–8 H2 sections | Many sibling pages under 40 lines each |
| Sidebar leaf = substantive chapter | Nav entry that is only a link hub |
| Mintlify auto-TOC from headings | Deep nav trees (3+ levels of leaves) |
| Redirect old URL → `page#section` | Orphan URLs with no redirect |

**Minimum leaf page:** ~4 H2 sections or 80+ lines of useful content.

**Exceptions:** Integrations Hub per-integration reference (`integrations-hub/*`), Reference (API, glossary), and standalone consumer guides (e.g. invoke from Claude).

### Primary axis = product journeys

| Pillar | Canonical home |
|--------|----------------|
| Get started | Onboarding, workspace model, users & roles |
| Core concepts | `concepts/overview` (one file, H2 per concept) |
| Build | Graph Studio, DevStudio, Triggers & Intents |
| Connect | Channels guide + Integrations Hub catalog |
| Ship | `builds/guide` |
| Operate | Observability + `support/troubleshooting` |
| Agent Registry | `agent-registry/overview`, `publish`, `compose`, `invoke-a2a-from-claude` |
| Reference | API, glossary, MCP assistant |

`concepts/overview` explains **what**; studio sections explain **how**. Do not duplicate procedures in concept sections.

### One canonical URL per topic

- **Agent graph** (not "flow" in user-facing prose)
- **Graph Studio** (not "Workflow Builder" in sidebar)
- **Aura** = Graph Studio AI assist; **Copilot** = DevStudio tool generation
- **Integrations:** `integrations-hub/*` only in nav (not `devstudio/prebuilt/*`)

### Redirects

When merging pages, add `docs.json` redirects:

```json
{ "source": "/old/path", "destination": "/new/guide#section-anchor" }
```

Update inline links in markdown to the canonical URL; do not rely on redirects alone for primary navigation.

## Documentation tab map

```
1. Get started
2. Core concepts → concepts/overview
3. Build
   ├── Graph Studio (8 leaves)
   ├── DevStudio (5 leaves)
   └── Triggers & Intents (3 leaves)
5. Ship → builds/guide
6. Operate
7. Agent Registry (A2A) (4 leaves)
8. Reference
```

## Connect tab map

```
Overview → connect/overview, integrations-hub/overview
Channels → channels/guide
Integrations Hub → category subgroups (unchanged)
```

## Audience

Docs readers are **already signed in**. Do not promote `setup-account/signing-up` or first-workspace signup in nav or homepage cards.

## Related

- [Agent Registry contributor guide](agent-registry-docs-from-flow-gen-frontend.md)
- [Nomenclature change log](../nomenclature-change-log.md)
