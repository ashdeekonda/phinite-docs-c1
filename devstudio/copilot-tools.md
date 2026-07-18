---
title: "Copilot-Generated Tools"
description: "Use prompt-based generation to scaffold tools quickly in Dev Studio."
---

Dev Studio **Copilot** drafts Python tool handlers from a natural-language spec. Review and harden the scaffold before you [publish](/devstudio/versioning) and attach it to an Agent Graph node.

<Frame caption="Dev Studio Copilot — describe the tool and review generated code">
  <img src="/images/image.png" alt="Dev Studio Copilot tool generation panel" />
</Frame>

## Generate a tool with Copilot

1. Open **Dev Studio** from workspace **Tools** (new or existing tool).
2. Open the **Copilot** panel and describe the tool:
   - Purpose and when the agent should call it
   - Expected **inputs** (session variables) and **outputs**
   - Target system (API, database, messaging app)
3. Review the generated handler, parameter schema, and error handling.
4. Edit validation, secrets access (`env_variables`), and return shape to match [tool structure](/devstudio/structure).
5. [Test](/devstudio/testing-tools) with realistic sample JSON, then **Publish** a version.

<Tip>
  Use realistic sample inputs and verify expected outputs before publishing. Copilot scaffolds are a starting point—not production-ready without review.
</Tip>

## Related

- [Manual coding (Python)](/devstudio/manual-coding)
- [Custom tools](/devstudio/custom-tools)
- [Testing tools](/devstudio/testing-tools)
