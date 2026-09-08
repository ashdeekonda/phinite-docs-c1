---
title: Guardrails overview
description: LLM safety profiles — workspace Guardrails analytics and Studio LLM Governance.
---

**Guardrails** inspect prompts and model output for injection, toxicity, and data leaks before a turn completes. In the product IA:

- Workspace: **OPERATE → Governance → Guardrails** (analytics + library context)
- Studio: **Governance → LLM Governance** (create, attach, In Use / Library) — not a separate Studio rail

<Note>
  Guardrails share the **Pro+** Governance entitlement (`MinPlan.Governance` / `MinPlan.Guardrails`). Attach and profile CRUD use `workspace.governance.*`.
</Note>

<CardGroup cols={2}>
  <Card title="Create profiles" href="/guardrails/profiles">
    Providers, credentials, Phinite control library, Save profile.
  </Card>
  <Card title="Attach to flows" href="/guardrails/attach">
    Attach guardrails to entire flow or one agent.
  </Card>
  <Card title="Governance" href="/governance/overview">
    Tool policies and HITL (sibling Operate surface).
  </Card>
  <Card title="Observability" href="/observability/insights">
    Policy blocks and session drill-down.
  </Card>
</CardGroup>

## Where in the product

| Surface | Entry |
| --- | --- |
| Workspace analytics | `…/governance?tab=guardrails` |
| Studio module | Graph Studio → **Governance** → **LLM Governance** (`?tab=governance`) |
| Legacy Studio tab | `?tab=guardrails` canonicalizes to Governance → LLM module |

<Frame caption="Studio LLM Governance — library of profiles">
  <img src="/images/v2/governance/06-studio-llm.png" alt="LLM Governance library" />
</Frame>

Workspace Guardrails tab:

<Frame caption="Workspace Governance — Guardrails">
  <img src="/images/v2/governance/02-workspace-guardrails.png" alt="Workspace Guardrails analytics" />
</Frame>

### Workspace analytics labels

**Guardrail activity** · Blocked / Logged · Decisions / Triggers · range **Last 7 / 30 / 90 days** · **Refresh**. Optional sessions drill-down with guardrail purpose.

## Studio LLM Governance

| UI | Meaning |
| --- | --- |
| **In Use (N)** | Profiles attached to this flow version |
| **Library (N)** | Workspace profiles — **Attach**, edit, delete |
| **New profile** / create | [Create profile wizard](/guardrails/profiles) |
| **Attach** | [Attach guardrails](/guardrails/attach) |

Prominence: *Inspects prompts and model output for injection, toxicity, and data leaks before a turn completes.*

## Providers at a glance

| Provider | UI label |
| --- | --- |
| `phinite` | **Phinite** |
| `aws` | **AWS Bedrock** |
| `azure` | **Azure Content Safety** |
| `gcp` | **GCP Model Armor** |

## APIs (summary)

Prefix under `/governance/guardrails/`: `providers`, `catalog`, `credentials`, `profiles`, `active`, remote-config, test connection. Bindings use `binding_type: "guardrail"`.

## Related

- [Profiles](/guardrails/profiles)
- [Attach](/guardrails/attach)
- [Governance overview](/governance/overview)
