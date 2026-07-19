---
title: Tool authoring methods
description: Build custom tools with Dev Studio Copilot or manual Python.
---

Choose how you author a custom tool before [testing and publishing](/devstudio/custom-tools).

## Copilot-generated tools

Dev Studio **Copilot** drafts Python handlers from a natural-language spec.

<Frame caption="Dev Studio Copilot">
  <img src="/images/image.png" alt="Copilot tool generation panel" />
</Frame>

1. Open **Dev Studio** from workspace **Tools**.
2. Describe purpose, **inputs**, **outputs**, and target system.
3. Review generated handler, parameters, and error handling.
4. Edit validation and return shape to match the [tool contract](/devstudio/custom-tools#tool-contract).
5. [Test](/devstudio/custom-tools#test-tools), then **Publish**.

<Tip>
  Copilot scaffolds need review before production. Write a clear tool **description** — agents use it to decide when to call the tool.
</Tip>

## Manual Python

Use manual coding when Copilot or a [predefined integration](/devstudio/prebuilt-tools) is not enough.

See the full [tool contract and example](/devstudio/custom-tools#tool-contract) on the Custom tools page.

## When to use which

| Method | Best for |
| --- | --- |
| **Copilot** | Quick CRUD wrappers, prototypes |
| **Manual** | Complex rules, compliance-sensitive logic |
| **Both** | Generate scaffold, then hand-edit before publish |

## Related

- [Custom tools](/devstudio/custom-tools)
- [Tools & Dev Studio overview](/devstudio/overview)
