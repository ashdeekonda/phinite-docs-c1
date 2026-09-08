---
title: LLM guardrails
description: Attach guardrail profiles under Studio LLM Governance (not a separate Guardrails rail).
---

**LLM Governance** is where guardrail profiles attach to an Agent Graph. Workspace **Governance → Guardrails** holds the library; Studio applies profiles to the current flow.

<Info>
  In this product IA, Guardrails are folded into **LLM Governance**. There is no separate Studio “Guardrails” rail.
</Info>

<Frame caption="Studio LLM Governance — library of guardrail profiles">
  <img src="/images/v2/governance/06-studio-llm.png" alt="LLM Governance with Attach, New profile, and provider profiles" />
</Frame>

## Providers and profiles

Profiles in the library show a provider badge, for example:

- **Phinite**
- **GCP Model Armor**
- **AWS Bedrock**
- **Azure Content Safety**

Use them to inspect prompts and outputs for toxicity, sensitive data, and similar risks. Exact guards and actions (deny / observe / steer) depend on the profile configuration.

## Attach in Studio

1. Open **Governance → LLM Governance**.
2. Under **Library**, click **Attach** on a profile, or **New profile**.
3. Confirm the profile appears under **In Use** for this flow version.
4. **Save** the Agent Graph before **Build**.

From **Summary**, the **LLM Governance** card shows whether anything is attached yet.

## Workspace Guardrails tab

<Frame caption="Workspace Governance — Guardrails library">
  <img src="/images/v2/governance/02-workspace-guardrails.png" alt="Workspace Guardrails tab" />
</Frame>

Manage and review profiles at the workspace level, then attach them per graph in Studio. Analytics on the **Policies** tab remain focused on tool-policy enforcement; treat Guardrails as the LLM safety library.

## Related

- [Governance overview](/governance/overview)
- [Tool policies](/governance/tool-policies)
- [Approvals](/governance/approvals)
