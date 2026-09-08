---
title: Tool policies
description: Allow, deny, and human_approval rules for tools on an Agent Graph.
---

**Tool Governance** attaches reusable tool-access policies to a flow version. Each policy is a set of rules that **allow**, **deny**, or require **human approval** for tool calls.

<Frame caption="Studio Tool Governance — In Use and Library">
  <img src="/images/v2/governance/05-studio-tool.png" alt="Tool Governance panel with attached ash-test policy and library" />
</Frame>

## Rule effects

| Effect | Behavior |
| --- | --- |
| **allow** | Tool call proceeds |
| **deny** | Tool call is blocked |
| **human_approval** | Tool call waits for a person (HITL) before continuing |

Policy cards summarize rule counts (for example `3 rules, 1 approval, 2 deny`).

## Attach a policy in Studio

1. Open the Agent Graph → **Governance** → **Tool Governance**.
2. Under **Library**, find a policy (or create one from workspace Governance).
3. Click **Attach**.
4. If the policy includes human-approval rules, set **Approval delivery** to **Dashboard** and/or **Email**.
5. Optionally **Attach HIL** profiles so approvers and channels are defined.
6. **Save** the graph when Studio prompts you.

**In Use** lists policies on the current flow version with **Edit** and **Detach**.

## Human in the Loop

The **Human in the Loop** tab shows policies that need a person and whether HIL profiles are linked. Empty states send you back to **Tool Governance** to attach channel/user profiles.

<Frame caption="Studio Human in the Loop — linked policies">
  <img src="/images/v2/governance/07-studio-hitl.png" alt="Human in the Loop tab with linked tool policy" />
</Frame>

<Warning>
  Slack/Teams as HIL delivery channels are not documented as production delivery here. Use **Dashboard** and **Email** approval delivery shipped with the product.
</Warning>

## Workspace Policies tab

**OPERATE → Governance → Policies** shows fleet metrics: policy decisions (blocked vs logged), approvals resolved, sessions with policy events, and rule mix across configured policies. Use it to spot hotspots, then fix bindings in Studio.

## Related

- [Governance overview](/governance/overview)
- [Approvals](/governance/approvals)
- [LLM guardrails](/governance/llm-guardrails)
