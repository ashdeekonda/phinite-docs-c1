---
title: "BYOK docs — source of truth (internal)"
description: "Internal guide for maintaining Model Keys / BYOK documentation from flow-gen-frontend, api-server-2, and api-gateway."
hidden: true
---

## Audience

These notes are for **internal** writers, solutions engineers, and agents updating Mintlify. Customer-facing pages live under `/byok/*`.

**Shared authoring rules:** [`public-documentation-rules.md`](public-documentation-rules.md) (tone, `docs.json`, nomenclature, quality gate). Public BYOK pages follow the same instructional style as `agent-registry/expose-your-flow.md`—not meta or internal voice.

## Repos

| Repo | What to verify |
| ---- | -------------- |
| `flow-gen-frontend` | Labels, modals, drawers, permissions, toasts |
| `api-server-2` | `/byok` routes, encryption, `orchestrationModelSecrets`, billing `ownKey` |
| `api-gateway` | Proxied routes (no DELETE today) |
| `docs` | `docs.json` navigation + cross-links |

## Primary UI surfaces

| Surface | Route / entry | Key files |
| ------- | ------------- | --------- |
| **Model Keys** | `/{org}/workspace/{id}/model-key` | `model-key/page.tsx`, `ProductApiKeyDrawer.tsx` |
| **Change model** | Graph Studio → agent node | `ChangeApiModal.tsx` |
| **Add key (studio)** | `+ Add New Key` from Change model | `AddModelProviderKeyDrawer.tsx` |

Legacy redirect: `/product-api` → `/model-key`.

## Exact UI copy catalog

### Sidebar & page header

| UI string | Context |
| --------- | ------- |
| **Model Keys** | Sidebar + page title |
| **Model keys (BYOK — bring your own key)** | `PageTooltip` (`pageKey="modelKeys"`) — full tooltip body documents Anthropic/Azure/Gemini examples |
| **(N) keys** | Count next to title |
| **Search keys** | Search placeholder |
| **Default Model:** | Header dropdown label |
| **Select default model** / **Updating…** | Dropdown placeholder states |
| **+ New Key** | Primary CTA (`title`: Add a new Product API key) |

### Phinite Key card

| UI string | Context |
| --------- | ------- |
| **Phinite Key** | Card name |
| **Built-in** | Badge on static card |
| **Make it Default** / **Saving…** | Secondary button |
| **Phinite is already the default key** | Disabled tooltip |

### Custom key cards

| UI string | Context |
| --------- | ------- |
| **{provider} (default)** | Uppercase provider + default suffix |
| Masked secret | `****…****` style from `maskKey()` or `*************************` from API |
| **View key details** | Eye icon |
| **Edit key** | Pencil icon |
| **Copy Product API key to clipboard** | Copy icon → toast **Copied!** / **Failed to copy** |

### Empty / error states

| UI string | Context |
| --------- | ------- |
| **Could not load BYOK keys:** | List error banner |
| **Access Denied** | No `workspace.api_keys` read |
| **You don't have permission to view Product API keys.** | Permission copy |
| **Loading model keys…** | Empty state |
| **No matching keys. Try another search.** | Search miss |

### Model Provider Key drawer (workspace)

| UI string | Context |
| --------- | ------- |
| **Add a Model Provider Key** | Create sheet title |
| **Edit a Model Provider Key** | Edit sheet title |
| **View Model Provider Key** | View sheet title |
| **Name of the Key** | Field label |
| **Select Provider** | Field label |
| **Loading providers…** / **Loading provider fields…** | Loading |
| **No BYOK fields are required for the selected provider.** | Empty schema |
| **Make Default Provider+Key for future** | Checkbox |
| **This action will override any other previous defaults.** | Warning when default checked |
| **Create** / **Creating...** / **Update** / **Updating...** | Footer CTA |

Field labels are **humanized** from `byokConfig` keys (`api_key` → **API Key**).

### Change model modal (Graph Studio)

| UI string | Context |
| --------- | ------- |
| **Change model** | Modal title |
| **Resource** | Dropdown (text, image, …) |
| **Operation** | Segmented **Generate** / **Analyze** |
| **Bring your own key(BYOK)** | Toggle label (exact casing) |
| Tooltip | *Turn on Bring your own key (BYOK) to use an API key you configure. Leave it off to use platform-managed Phinite credentials.* |
| **Model Provider** | Shown when BYOK on |
| **Model** | Model dropdown |
| **Select Your Key(BYOK)** | Key dropdown when BYOK on |
| **+ Add New Key** | Opens studio drawer |
| Placeholders | *Select a model provider first*, *Loading keys…*, *No keys for this provider*, *Select a key* |
| **Cancel** / **Done** | Footer (not “Save”) |

### Add Model Provider Key drawer (studio)

| UI string | Context |
| --------- | ------- |
| Same field labels as workspace drawer | |
| **This Provider and key will be used as default for all future agent nodes added.** | Studio-only helper under default checkbox |
| **Test** / **Testing** | Test connection (`POST /byok/test-connection`) |
| **Done** | Create after test |
| Toast | *Saved "{name}".* |

## Technical mapping (what the FE exposes)

| UI concept | Stored / sent | API |
| ---------- | ------------- | --- |
| Phinite toggle off | `developMode: "phinite"`, `byokid: null` | No provider fetch |
| BYOK toggle on | `developMode: "self"` | Requires provider + key |
| Selected key | `envEncryptId` in modal state → `byokid` on save | `GET /byok?provider=…` |
| New key from studio | `byokid` + optional `apiKey` JSON on save | `POST /byok`, `test-connection` |
| Workspace default | `isDefault` on record | `PUT /byok/{id}` or Phinite POST |
| List display | Masked `value` | `GET /byok` |
| Copy / view | Full secret | `GET /byok/{byokid}` |

Permissions: API `workspace.byok`; UI `workspace.api_keys` + `workspace.sidebar.api_keys`.

## Doc maintenance checklist

- [ ] Tooltip text matches `PageToolTips.tsx` → `modelKeys`
- [ ] Modal title is **Change model**, not “Change API”
- [ ] Operation **Generate** / **Analyze** documented for image/video constraints
- [ ] Plan copy: **BYOK (Bring Your Own Keys)** in `PlanSelection.tsx` vs subscription `features.byok`
- [ ] Delete remains undocumented as user-facing until gateway + UI ship
- [ ] Run `mint broken-links` after edits

## Screenshots

Capture list for public docs: [`images/byok/README.md`](../images/byok/README.md). Comparison draft with placeholders: `byok-v2/*`.

## Mintlify pages

| Page | Path |
| ---- | ---- |
| Overview | `byok/overview.md` |
| Model Keys workspace UX | `byok/managing-model-keys.md` |
| Graph Studio UX | `byok/graph-studio-byok.md` |
| Billing | `byok/billing-and-usage.md` |
| Glossary | `byok/glossary.md` |
| API & permissions (draft) | `byok-v2/api-and-permissions.md` |
