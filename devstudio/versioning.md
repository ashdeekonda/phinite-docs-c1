---
title: "Tool Versioning"
description: "Draft, publish, rollback, and pin tool versions for Agent Builds."
---

Dev Studio tools are **versioned artifacts**. Only **published** versions appear in Graph Studio tool pickers and can be pinned when you **Build** an Agent Graph.

## Version workflow

1. **Draft** — edit handler code and parameters in Dev Studio.
2. **Test** — run sample inputs in [Dev/UAT/Prod](/devstudio/testing-tools).
3. **Publish** — create an immutable version with release notes.
4. **Attach** — enable the published version on agent nodes ([linking tools](/devstudio/linking-tools)).
5. **Build** — pin tool versions into an Agent Build for deploy.

<CardGroup cols={2}>
  <Card title="Test before publish" icon="flask" href="/devstudio/testing-tools">
    Catch parameter and credential issues early.
  </Card>
  <Card title="Build pinning" icon="box" href="/builds/overview">
    Builds freeze graph + tool versions together.
  </Card>
</CardGroup>

## Best practices

- Use semantic version labels and clear **version notes** (what changed, breaking diffs).
- Test in **Dev**, validate in **UAT**, then publish for production builds.
- Keep prior versions available for rollback when a deploy regresses.

## Rollbacks

1. Identify the last known-good published version in Dev Studio **Versions**.
2. Re-attach that version on affected agent nodes in Graph Studio.
3. **Save**, create a new **Build**, and redeploy to the target environment.

<Tip>
  Unpublished tools show **Publish** in the **Build** dialog. Resolve them before shipping to UAT or Prod.
</Tip>

## Related

- [Custom tools — publishing](/devstudio/custom-tools)
- [Common build failures](/support/build-failures)
