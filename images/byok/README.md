# Placeholder screenshots for BYOK (Model Keys) documentation

Capture these images from a workspace on **Professional** or higher (BYOK enabled). Use the same org/workspace across all shots so provider names stay consistent.

**Internal capture guide:** [`contributing/byok-docs-from-flow-gen-frontend.md`](../../contributing/byok-docs-from-flow-gen-frontend.md)

| File | Screen to capture |
| ---- | ----------------- |
| `overview-hero.png` | **Model Keys** — full page with **Phinite Key** card and at least one custom key |
| `model-keys-sidebar.png` | Sidebar with **Model Keys** selected (show **API Keys** nearby for contrast) |
| `model-keys-header.png` | Page header — title, key count, **Search keys**, **Default Model**, **+ New Key** |
| `phinite-key-card.png` | **Phinite Key** card — **Built-in** badge, masked line, **Make it Default** |
| `custom-key-card.png` | Custom key card — provider label, masked secret, **View** / **Edit** / **Copy** actions |
| `default-model-dropdown.png` | **Default Model** dropdown open — **Phinite Key** and custom keys listed |
| `add-key-drawer-workspace.png` | **Add a Model Provider Key** sheet from **+ New Key** (provider + credential fields visible) |
| `change-model-modal-phinite.png` | Graph Studio — **Change model** with **Bring your own key(BYOK)** **off** |
| `change-model-modal-byok.png` | **Change model** with BYOK **on** — **Model Provider**, **Model**, **Select Your Key(BYOK)** |
| `change-model-add-key.png` | **+ Add New Key** panel beside **Change model** (studio drawer) |
| `test-connection-studio.png` | Studio add-key panel — **Test** / **Testing** state or success before **Done** |
| `agent-node-change-model-entry.png` | Agent node panel showing how to open **Change model** |
| `billing-usage-context.png` | **Billing** or **Token usage** view with a note in caption if BYOK vs Phinite Key is not visually distinct |

Recommended viewport: **1440×900** (or consistent width across all shots). Use light theme unless documenting dark-mode-specific UI.

**Suggested demo data (optional):** one Azure text key named `docs-azure-prod`; one agent node on **text** + **Generate** with BYOK on and that key selected.
