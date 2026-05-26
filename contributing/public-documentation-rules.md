---
title: "Public documentation rules (Phinite)"
description: "Authoring standards for customer-facing Mintlify docs—tone, structure, repo conventions, and workflows."
hidden: true
---

Use this document when writing or reviewing **public** pages under `docs/`. It extends the generic Mintlify guidance in [`docs/.cursor/rules.md`](../.cursor/rules.md) with **Phinite-specific** rules from this repository.

**Published navigation is controlled by [`docs/docs.json`](../docs.json).** Update it on every page add, rename, or removal.

---

## 1. Tone and style

### Voice
- Use **second person** ("you") and **active voice**.
- Lead with **why** (outcome, risk, or prerequisite), then **how** (steps).
- Use **imperatives** for actions: Open, Select, Publish—not passive or hedged phrasing.

### Language
- Plain, global English. Aim for **sentences under 20 words**.
- Avoid idioms, hype ("powerful", "seamless"), and unexplained internal field names.
- **Bold UI labels** on first use in a section: **Model Keys**, **Change model**, **Phinite Key**.
- Do **not** use internal/meta voice in public pages: no "your narrative", "customers often", "internal reference", or CS script blocks.

### Audience split

| Audience | Location | Tone |
| -------- | -------- | ---- |
| Customers | `docs/**/*.md` listed in `docs.json` | Instructional, neutral, confident |
| Internal writers | `docs/contributing/*.md` with `hidden: true` | UI copy catalogs, file maps, API truth |

Files listed in [`.mintignore`](../.mintignore) are not published—see [Excluded paths](#excluded-paths).

---

## 2. Gold-standard pages (copy this shape)

| Pattern | Example path |
| ------- | ------------- |
| Feature overview + CardGroup | `agent-registry/overview.md` |
| Wizard / how-to with UI step table | `agent-registry/expose-your-flow.md` |
| Prerequisites + Steps + screenshots | `getting-started/quickstart.md` |
| Operational depth + role tables | `graph-studio/publishing.md` |
| Glossary (UI vs API terms) | `agent-registry/glossary.md`, `byok/glossary.md` |

Do **not** treat `docs/essentials/` or `/tmp/mintlify-starter-ref/` as templates for customer content. They are stale or generic Mintlify samples.

---

## 3. Mintlify structure (Phinite conventions)

### Frontmatter (required on every public page)

```yaml
---
title: "Page title (becomes H1)"
description: "One sentence for SEO and subtitle."
icon: "lucide-name"    # optional; match sibling pages
keywords: ["optional"] # optional; internal search
---
```

- **Never** add a manual `# H1` in the body.
- Body starts at `##`. Do not skip heading levels.

### Recommended page flow (how-to / feature)

1. Short intro — what this page covers and when to use it.
2. **Prerequisites** — roles, plan, published assets, environment.
3. **Procedure** — numbered steps or `<Steps>`; match **exact UI labels**.
4. **Reference** — tables (errors, parameters) only when needed.
5. **Related** — `<CardGroup>` or links to 2–4 sibling pages.

### Components used in this repo

Prefer components already used in Phinite docs. Full syntax: [`docs/.cursor/rules.md`](../.cursor/rules.md).

| Component | Use when | Seen in |
| --------- | -------- | ------- |
| `<Steps>` / `<Step>` | 3+ sequential UI steps | `quickstart.md`, BYOK, Agent Registry |
| `<Check>` | Pre-publish checklists | `graph-studio/publishing.md` |
| `<Warning>` | Security, permissions, irreversible actions | `workspaces/workspace-overview.md` |
| `<Info>` / `<Note>` | Context and caveats | Throughout |
| `<Tip>` | Best practices (sparingly) | `workspaces/workspace-overview.md` |
| `<CardGroup>` + `<Card>` | Hub / next steps | `agent-registry/overview.md`, `index.md` |
| `<Frame>` + `![alt](path)` | Screenshots | `agent-registry/expose-your-flow.md` |
| Mermaid | Simple end-to-end flows | `agent-registry/overview.md` |

Use `<Accordion>`, `<Tabs>`, `<CodeGroup>`, `<Prompt>`, `<Visibility>` only after a deliberate docs-wide adoption—not copied ad hoc from the Mintlify starter.

### Scannability
- Max 3–4 sentences per paragraph.
- Prefer bullets and tables over prose walls.
- One callout type at a time; do not stack more than two adjacent callouts.

---

## 4. Navigation, links, and URLs

### `docs.json` (mandatory)

| Action | Required |
| ------ | -------- |
| Add a page | Add path to correct `group` / nested `group` in [`docs.json`](../docs.json) |
| Rename/move a page | Update path **and** add `redirects` entry |
| Delete a page | Remove from `docs.json`; add redirect if URL was public |

- Paths have **no** extension: `"byok/overview"` → `byok/overview.md`.
- Mintlify navigation patterns: [Mintlify — Navigation](https://www.mintlify.com/docs/organize/navigation).

### Link rules
- Root-relative links: `/graph-studio/overview`, not `./overview`.
- Cross-link related modules when adding a feature area (`index.md`, overview, glossary, Graph Studio).
- After edits, run from `docs/`: `mint broken-links --check-anchors --check-redirects`.

### Legacy URL redirects

[`docs.json`](../docs.json) includes **`/flowgen/*` → `/graph-studio/*`** redirects. Do not introduce new `/flowgen/` links. See [Nomenclature](#nomenclature-and-product-terms).

### Homepage hub

[`index.md`](../index.md) uses `<CardGroup>` for discovery. Add a card when shipping a major new doc section.

---

## 5. Nomenclature and product terms

Authoritative list: [`nomenclature-change-log.md`](../nomenclature-change-log.md).

| Prefer in docs | Avoid (legacy) |
| -------------- | -------------- |
| **Graph Studio** | Flowgen, FlowGen Studio |
| **Agent Graph** / **Agent Graphs** | Flow / Flows (when meaning orchestration) |
| **Agent Node** | Agent Block (docs term) |
| **master node**, **child node**, **tool node**, **end node** | master-agent block, etc. |

### UI label ≠ doc term

When the product UI still shows an old label, document both once—example from Agent Registry:

- UI: **Agent Block** (browse panel)
- Docs: **Agent Node** (preferred)

See `agent-registry/overview.md` and module glossaries.

### Spelling and locale
- Use **Organisation** when quoting UI copy that uses British spelling.
- Keep **React Flow** as the library name (do not substitute "React Agent Graph")—see nomenclature log corrections.

---

## 6. Four-repo accuracy (source of truth)

Before publishing, verify against:

| Repo | Verify |
| ---- | ------ |
| **flow-gen-frontend** | Sidebar labels, routes, modal titles, tooltips, permissions, dev-only gates |
| **api-server-2** | API paths, RBAC modules (`workspace.byok`, etc.), billing flags, models |
| **api-gateway** | Proxied routes only—omit endpoints not exposed (e.g. some DELETE routes) |
| **docs** | `docs.json`, redirects, cross-links, nomenclature |

Document **current product behavior**, not roadmap. Use `<Note>` for unreleased UI (commented delete buttons, dev-only features).

### Module contributor guides (internal)

Use these when maintaining a feature area—they list primary source files and accuracy checklists:

| Module | Guide |
| ------ | ----- |
| Agent Registry (A2A) | [`contributing/agent-registry-docs-from-flow-gen-frontend.md`](agent-registry-docs-from-flow-gen-frontend.md) |
| Model Keys (BYOK) | [`contributing/byok-docs-from-flow-gen-frontend.md`](byok-docs-from-flow-gen-frontend.md) |

Pattern for new modules: `contributing/<feature>-docs-from-flow-gen-frontend.md` + optional `images/<feature>/README.md` screenshot checklist.

---

## 7. Images and media

- Store public assets under `docs/images/<feature>/`.
- Every `![alt](/images/...)` path must have a real file before release, or keep the image out until capture.
- Screenshot checklist example: [`images/agent-registry/README.md`](../images/agent-registry/README.md) (viewport **1440×900**, light theme unless documenting dark mode).
- Meaningful `alt` text; no secrets in screenshots.

---

## 8. Excluded paths

[`.mintignore`](../.mintignore) excludes from publish and link checks:

- `.cursor/` — stale nav; not customer docs
- `essentials/` — Mintlify starter leftovers
- `contributing/**` — internal guides (this file)
- `support-chatbot-knowledge-rack.md` — RAG/support corpus, not sidebar nav
- `link-audit-report.txt`, `emails/**`

---

## 9. Workflow prompts

### Translate code to doc (API / config)

**Output:**
1. Two-sentence summary (what + when).
2. Prerequisites (auth, permission, plan flag).
3. Parameter table: `Parameter` | `Type` | `Required` | `Description`.
4. Response example (JSON if helpful).
5. Errors table: message → cause → action.
6. Related links to UI how-to pages.

Extract types from code; do not invent fields. If UI name ≠ API name, document both in one small table.

### Simplify technical draft

Rewrite engineering notes for external readers:

- [ ] Remove ticket IDs, internal codenames, and file paths unless needed for integration docs
- [ ] Lead with user outcome, then steps
- [ ] Move raw field names to a table or glossary
- [ ] Add Prerequisites and Related sections
- [ ] Security: encryption, masking, who can view/copy secrets
- [ ] Plan/permission limits in `<Warning>` or `<Info>`
- [ ] Apply [nomenclature](#nomenclature-and-product-terms) rules

### Write feature overview (new module)

Deliverables: `overview.md` + 2–4 task pages + optional `glossary.md`.

1. Register all paths in `docs.json`.
2. Overview: intro, fit in product (diagram/table), prerequisites, `<CardGroup>` next steps.
3. Task pages: follow `expose-your-flow.md` shape.
4. Add `contributing/<feature>-docs-from-flow-gen-frontend.md` for internal maintainers.
5. Update `index.md` and cross-links (`graph-studio/`, `workspaces/`, etc.).

### Review doc tone (reject if present)

- Meta voice ("what users see", "internal teams", "your narrative")
- Bold on every UI string in one sentence
- API-first lead with no user outcome
- Broken image paths without assets
- Missing `docs.json` entry
- `/flowgen/` links or "Flowgen" in prose

---

## 10. Quality gate before merge

- [ ] `title` + `description` frontmatter; no body H1
- [ ] [`docs.json`](../docs.json) updated; `redirects` if URL changed
- [ ] Links root-relative; targets exist
- [ ] UI labels spot-checked against `flow-gen-frontend`
- [ ] Nomenclature per [`nomenclature-change-log.md`](../nomenclature-change-log.md)
- [ ] `mint broken-links` (from `docs/`) when CLI available
- [ ] No real secrets in examples or screenshots
- [ ] Internal-only detail lives in `contributing/` with `hidden: true`

---

## 11. External references

| Resource | URL |
| -------- | --- |
| Mintlify docs index | https://www.mintlify.com/docs/llms.txt |
| Navigation | https://www.mintlify.com/docs/organize/navigation |
| Pages / frontmatter | https://www.mintlify.com/docs/organize/pages |
| Components | https://www.mintlify.com/docs/components |
| mintignore | https://www.mintlify.com/docs/organize/mintignore |
| Mintlify CLI | https://www.mintlify.com/docs/cli/commands |

Local preview: `cd docs && mint dev`.

---

## One-line agent reminder

> Write like `expose-your-flow.md`: you/your, prerequisites first, bold UI labels in steps, verify FE+BE+gateway, update `docs.json` on every page change, follow `nomenclature-change-log.md`, keep internal copy in `contributing/` only.
