---
title: Guardrail profiles
description: Create LLM guardrail profiles — Provider, Configure, credentials, Phinite control library.
---

Create profiles from Studio **Governance → LLM Governance → New profile** (or the workspace Guardrails library entry points that open the same panel).

## Create profile wizard

### 1. Provider

Choose a provider, then **Continue**:

| id | Label | Credentials | Resource |
| --- | --- | --- | --- |
| `phinite` | **Phinite** | None — uses **Control library** | — |
| `aws` | **AWS Bedrock** | **Access key ID**, **Secret access key**, **Region** | **Guardrail ID**, **Guardrail version** |
| `azure` | **Azure Content Safety** | **Endpoint URL**, **API key** | — |
| `gcp` | **GCP Model Armor** | **Service account JSON**, **Project ID**, **Location** | **Template / policy ID** |

### 2. Configure

**Profile name** (placeholder `e.g. Production guards`).

#### Non-Phinite providers

1. Open **Credentials**.
2. **How do you want to provide secrets?** → **Enter credentials** or **Use Environment secret**.
3. Fill **Secret \*** and **Resource** fields for the provider.
4. Optional **Test connection**.
5. Use **Documentation** / **\{Provider\} setup guide** if shown.
6. Click **Save profile**.

Default violation handling field: `on_violation` (product default **block_turn**).

#### Phinite provider — Control library

1. Open **Control library**.
2. **Turn on the guards this profile should enforce**.
3. Tracks appear under **Before the model**, **After the model**, and **Session data**.
4. Per guard actions: **Block** · **Log only** · **Redact**.
5. **Save profile**.

## After save

- Profile appears in **Library (N)** on **LLM Governance**.
- [Attach](/guardrails/attach) it to the current flow or a single agent.
- Workspace **Guardrails** analytics reflects activity after traffic runs.

## Related

- [Guardrails overview](/guardrails/overview)
- [Attach guardrails](/guardrails/attach)
- [Governance](/governance/overview)
