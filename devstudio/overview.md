---
title: "DevStudio Overview"
description: "Build, version, test, and publish tools that your agents can call."
---

## What is DevStudio?

<Frame>
  <img src="/images/Tools-overview.png" alt="Descriptive alt text" />
</Frame>

DevStudio is where you build tools—reusable, versioned functions your agent graphs and assistants call (send email, query CRMs, post to Slack, and more).

Open **Dev Studio** from an assistant's **Build → Tools**, or manage **Workspace Tools** from the workspace sidebar.

## Dev Studio sidebar

- **Tools** — Tool list and editor
- **Variables** — Tool-scoped variables
- **Versions** — Saved tool versions
- **Phinite Aura** — Generate or edit tool logic in natural language

## Key capabilities

- **Tool authoring**: Prompt-generated or manual coding
- **Type-safe parameters**: Define input/output schemas
- **Versioning**: Draft, **Save as Version**, rollback
- **Testing**: Run tools with sample inputs in multiple environments

<CardGroup cols={2}>
  <Card title="Ways to Build Tools" href="/devstudio/methods" icon="sparkles">
    Phinite Aura-generated or manual coding
  </Card>
   <Card title="Tool Types" href="/devstudio/types" icon="wrench">
    Custom, system, and structure tools; predefined tools via Integrations
  </Card>
</CardGroup>

## Best practices

- Validate inputs and handle errors defensively
- Log key steps for observability
- Keep secrets out of code; use environment variables
- Increment version numbers with meaningful notes