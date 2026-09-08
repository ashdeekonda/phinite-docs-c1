# Old IA coverage map (keep when skipping)

**Enrichment standard (Pass 4):** `<Frame caption>` on images; `<CardGroup>`/typed `<Card>`; `<Note>`/`<Tip>`/`<Info>`/`<Warning>`; markdown **numbered lists** for procedures (no `<Steps>`); Agent Graph terminology; dialog depth per screen where applicable.

**Standing rule:** When we skip, collapse, or redirect a page, check it against the **old** Mintlify tree. Every skip must be **REDIR**, **DEFER**, **DROP**, or **DONE**.

## Pass 4 status (2026-07-19)

| Area | Nav pages | Content status | Nav wired |
| --- | --- | --- | --- |
| Getting Started | 4 | **DONE** | **DONE** |
| Agent Graphs | 3 | **DONE** | **DONE** |
| Graph Studio | 31 | **DONE** | **DONE** |
| Tools & Dev Studio | 17 | **DONE** | **DONE** |
| Configure | 5 | **DONE** | **DONE** |
| Ship | 27 | **DONE** | **DONE** |
| Observability | 11 | **DONE** | **DONE** |
| User Management | 5 | **DONE** | **DONE** |
| Reference | 5 | **DONE** | **DONE** |
| Support | 4 | **DONE** | **DONE** |
| Agent Registry tab | 8 | **DONE** | **DONE** |
| Integrations Hub tab | ~61 | **DONE** (terminology + Note) | **DONE** |

## Pass 5 status (2026-09-08) — ash/sep

| Area | Nav pages | Content status | Nav wired |
| --- | --- | --- | --- |
| RAG Collections | 3 (`rag/*`) | **DONE** | **DONE** |
| Observability | Insights + Investigate + existing | **DONE** (deepened) | **7. Observability** (top-level) |
| Governance | overview, tool-policies, hitl, approvals | **DONE** (deepened) | **8. Governance** (top-level) |
| Guardrails | overview, profiles, attach | **DONE** | **9. Guardrails** (separate chapter) |
| Evaluations | overview, studio, connect-to-build, run-on-draft | **DONE** (deepened) | **10. Evaluations** (top-level) |
| Custom Models / Models hub | +1 + models.md | **DONE** | Configure |

**REDIR:** `/governance/llm-guardrails` → `/guardrails/overview`; `/graph-studio/rag-management*` → `/rag/*`.  
**DEFER:** Budget Limits (Soon); HIL Slack/Teams as production delivery; Experiment wizard stub; sidebar Settings hub Phase 2.

**DROP (redirect only, not in nav):** `assistants/*` (11), `triggers-intents/intents*` (5), `reference/glossary`, `reference/ai-assistant`, spine stubs (`what-is-phinite`, `quickstart`, `studio/*`, legacy `a2a/*`, `agents/build-graph`, etc.). Note: live `rag/*` pages are **DONE** in Pass 5 (not DROP).

**DEFER (on disk, unreferenced):** `setup-account/*`, `assistants/*` legacy files, `workspaces/creating-workspace.md`

## Product DROPs (intentional)

- **Assistant** as top object → **Agent Graph**
- Email as create-type (filter chip may linger)
- Nav label **DevStudio** → **Tools & Dev Studio**
- **Intents** section removed from nav

## New nav (live)

See [`docs.json`](../../docs.json): groups **7–10** are Observability, Governance, Guardrails, Evaluations as separate top-level chapters (product UI still pockets Observability / Governance / Evaluations under OPERATE).
