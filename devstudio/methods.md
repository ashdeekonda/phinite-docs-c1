---
title: "Ways to Build Tools"
description: "Build tools via Copilot generation or manual Python coding in Dev Studio."
---

Choose how you author a tool before you [test](/devstudio/testing-tools) and [publish](/devstudio/versioning) it for Agent Graph nodes.

<CardGroup cols={2}>
  <Card title="Copilot-generated tools" icon="wand-magic-sparkles" href="/devstudio/copilot-tools">
    Describe inputs, outputs, and target systems; refine the scaffold in Dev Studio.
  </Card>
  <Card title="Manual coding (Python)" icon="code" href="/devstudio/manual-coding">
    Full control over handlers, validation, and external API calls.
  </Card>
</CardGroup>

## Methods compared

| Method | Best for | Trade-offs |
| --- | --- | --- |
| **Copilot-generated** | Bootstrapping CRUD wrappers, quick prototypes | Review generated code before publish |
| **Manual Python** | Complex business rules, sensitive integrations | More setup; maximum flexibility |

## Choose a method

1. **Start with Copilot** when you know the tool contract (inputs, outputs, external system) but want a fast first draft.
2. **Switch to manual coding** when you need fine-grained error handling, multi-step orchestration, or compliance-sensitive logic.
3. **Combine both** — generate a scaffold, then edit the Python handler and [structure](/devstudio/structure) before testing.

<Tip>
  Whichever method you use, write a clear tool **description**. Agent nodes use it to decide when to call the tool at runtime.
</Tip>

## Related

- [Tool types](/devstudio/types)
- [Custom tools](/devstudio/custom-tools)
- [Predefined tools](/devstudio/prebuilt-tools)
