---
title: "BYOK docs (comparison draft v2)"
description: "Deep BYOK draft with screenshot placeholders—compare against docs/byok/ before merge."
hidden: true
---

## What is different from `docs/byok/`

| Area | Published `byok/` | This draft `byok-v2/` |
| ---- | ----------------- | --------------------- |
| Screenshots | None | Placeholders + [`images/byok/README.md`](../images/byok/README.md) capture list |
| Structure | Shorter procedural pages | `<Steps>`-first procedures; bullets for reference; minimal tables |
| API | Summary table on managing page | Dedicated [api-and-permissions.md](./api-and-permissions.md) |
| UI labels | Normalized spelling | Exact FE strings e.g. **Bring your own key(BYOK)** |

## Pages

| Draft | Published |
| ----- | --------- |
| `overview.md` | `byok/overview.md` |
| `managing-model-keys.md` | `byok/managing-model-keys.md` |
| `graph-studio-byok.md` | `byok/graph-studio-byok.md` |
| `api-and-permissions.md` | *(new — split from managing page)* |
| `billing-and-usage.md` | `byok/billing-and-usage.md` |
| `glossary.md` | `byok/glossary.md` |

## Preview in Mintlify

**Not in `docs.json` by default.** To review locally, temporarily add a navigation group:

```json
"byok-v2/overview",
"byok-v2/managing-model-keys",
"byok-v2/graph-studio-byok",
"byok-v2/api-and-permissions",
"byok-v2/billing-and-usage",
"byok-v2/glossary"
```

## After review

1. Capture PNGs listed in `images/byok/README.md`.
2. Merge into `byok/` (or swap nav paths).
3. Register `api-and-permissions` in `docs.json` if kept as a separate page.
4. Remove this folder when no longer needed.
