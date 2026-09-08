---
title: Approvals
description: Triage human-in-the-loop approvals from the workspace inbox with dashboard and email delivery.
---

When a tool policy uses **human_approval**, runs pause until a person accepts or rejects. Approvers work from the workspace **Approvals** inbox and optional email; Studio configures **Approval delivery** on the policy binding.

<Frame caption="Workspace Governance — Approvals inbox">
  <img src="/images/v2/governance/03-workspace-approvals.png" alt="Governance Approvals tab" />
</Frame>

## Where to work approvals

| Surface | Use |
| --- | --- |
| **OPERATE → Governance → Approvals** | Primary inbox / triage |
| Studio **HIL Approvals** (sidebar) | Jump into approval work from Graph Studio |
| Email | When **Approval delivery** includes Email |

## Approval delivery

On **Tool Governance**, when attaching a policy that needs a person:

1. Open **Approval delivery** (or the attach wizard’s delivery step).
2. Enable **Dashboard** and/or **Email**.
3. Add email recipients when Email is on.
4. Save delivery, then finish attach.

<Note>
  Backend **Approval delivery** supports **Dashboard** and **Email** only. Studio **HIL New** may let you pick Slack/Teams destinations in the UI; treat those as preview until a profile delivery API ships.
</Note>

## Typical triage flow

1. Open **Governance → Approvals** (or follow a “Triage approvals” link from the Policies dashboard).
2. Review the pending tool call and context.
3. **Approve** or **Reject**.
4. Confirm the session continues or stops in [Observability](/observability/overview).

The Policies dashboard shows **Approvals resolved** (pending / approved / rejected) for the selected time range.

## Related

- [Tool policies](/governance/tool-policies)
- [Governance overview](/governance/overview)
- [Observability Insights](/observability/insights)
