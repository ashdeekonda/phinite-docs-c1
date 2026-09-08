---
title: Governance overview
description: Workspace policies and Studio Tool / HITL / LLM Governance for Agent Graphs.
icon: shield
---

**Governance** controls which tools agents may call, when a person must approve, and how LLM inputs/outputs are inspected. Use the workspace **OPERATE → Governance** dashboards for fleet health, and the Studio **Governance** panel to attach policies and profiles to a specific Agent Graph.

<Note>
  Governance (and Evaluations) require a **Pro+** plan (Professional or Enterprise). Lower tiers may show locked chrome in the Studio sidebar. The workspace **OPERATE → Governance** page is **Admin / Superadmin** only; Studio Governance read is available to roles with `workspace.governance.read`.
</Note>

<CardGroup cols={2}>
  <Card title="Tool policies" icon="screwdriver-wrench" href="/governance/tool-policies">
    Allow, deny, and human_approval rules on tools.
  </Card>
  <Card title="LLM guardrails" icon="shield-halved" href="/governance/llm-guardrails">
    Guardrail profiles under Studio LLM Governance.
  </Card>
  <Card title="Approvals" icon="inbox" href="/governance/approvals">
    Human approval inbox — dashboard and email delivery.
  </Card>
  <Card title="Observability" icon="chart-line" href="/observability/overview">
    Insights include policy blocks and session drill-down.
  </Card>
</CardGroup>

## Workspace vs Studio

| Surface | Role |
| --- | --- |
| **OPERATE → Governance** | Workspace analytics: Policies, Guardrails, Approvals (Budget is **Soon**) |
| **Graph Studio → Governance** | Per-flow Summary, Tool Governance, Human in the Loop, HIL New, **LLM Governance** |

<Frame caption="Workspace Governance — Policies tab">
  <img src="/images/v2/governance/01-workspace-policies.png" alt="Governance Policies dashboard with decisions and rule mix" />
</Frame>

Workspace tabs:

- **Policies** — decisions, approvals resolved, rule mix (ALLOW / HITL / DENY), code-execution profiles
- **Guardrails** — workspace library of LLM guardrail profiles (attach in Studio under **LLM Governance**)
- **Approvals** — triage pending human approvals
- **Budget** — marked **Soon** (out of scope for this release)

## Studio Summary

Open an Agent Graph, then **Governance** in the Studio sidebar (or `?tab=governance`). **Summary** shows attachment status for:

| Module | Purpose |
| --- | --- |
| **Tool Governance** | Tool access policies (allow / deny / human approval) |
| **Human in the Loop** | Tool policies that require a person before an action runs |
| **HIL New** | Profiles for where Accept/Reject lands (users / channels) |
| **LLM Governance** | Guardrail profiles (toxicity, data leaks, provider armor) |

<Info>
  **HIL New** channel profiles (Slack / Teams) are Studio UX ahead of API delivery. Shipped approval notification channels remain **Dashboard** and **Email** — see [Approvals](/governance/approvals).
</Info>

<Frame caption="Studio Governance Summary — attached Tool and HITL cards">
  <img src="/images/v2/governance/04-studio-summary.png" alt="Governance Summary with Tool Governance, HITL, HIL New, LLM Governance" />
</Frame>

Click **Open** on a card to jump to that submodule.

<Tip>
  Guardrails are **not** a separate Studio rail in this IA. Configure them under **LLM Governance** inside the Governance panel.
</Tip>

## Related

- [Tool policies](/governance/tool-policies)
- [LLM guardrails](/governance/llm-guardrails)
- [Approvals](/governance/approvals)
- [Evaluations overview](/evaluations/overview)
