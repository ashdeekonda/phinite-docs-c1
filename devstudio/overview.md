---
title: "DevStudio Overview"
description: "Build, version, test, and publish tools that your agents can call."
---

## What is DevStudio?

<Frame>
  <img src="/images/Tools-overview.png" alt="Descriptive alt text" />
</Frame>

DevStudio is where you build tools—reusable, versioned functions your flows and agents can call to take action (e.g., send emails, query CRMs, post to Slack).

## Key capabilities

- **Tool authoring**: Prompt-generated or manual coding
- **Type-safe parameters**: Define input/output schemas
- **Versioning**: Draft, publish, rollback
- **Testing**: Run tools with sample inputs in multiple environments

<CardGroup cols={2}>
  <Card title="Ways to Build Tools" href="/devstudio/methods" icon="sparkles">
    Copilot-generated or manual coding
  </Card>
   <Card title="Tool Types" href="/devstudio/types" icon="wrench">
    Custom and pre-built integrations
  </Card>
</CardGroup>

## Best practices

- Validate inputs and handle errors defensively
- Log key steps for observability
- Keep secrets out of code; use environment variables
- Increment version numbers with meaningful notes