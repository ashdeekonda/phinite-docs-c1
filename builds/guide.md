---
title: "Builds and environments"
description: "Manage build lifecycle, configuration, and deploy flows and tools across Dev, UAT, and Production."
---

## Overview and lifecycle

<Frame>
  ![Build](/images/Build.png)
</Frame>

A **build** is a versioned package of your flows and tools prepared for deployment to environments (Dev, UAT, Prod).

### Lifecycle stages

1. **Draft** — flows and tools under active development
2. **Validated** — passes checks and tests
3. **Published** — version created with notes
4. **Deployed** — running in target environment

### Promotion

- Promote Dev → UAT → Prod
- Require approvals for Prod
- Maintain rollback plans

After publishing, you can [expose agent graphs as A2A agents](/agent-registry/publish#expose-wizard) and promote exposed agents from test to live. See [Agent Cards & builds](/agent-registry/publish#agent-cards-and-builds).

## Publishing

Publishing creates a versioned artifact and deploys it to a target environment.

<Steps>
<Step title="Validate">
  Ensure all checks pass (lint, tests, validations).
</Step>
<Step title="Add version notes">
  Document changes for auditing.
</Step>
<Step title="Publish and deploy">
  Publish the version and deploy to the target environment.
</Step>
</Steps>

<Warning>
Production deployments require Admin or SuperAdmin role.
</Warning>

For step-by-step publishing in Graph Studio, see **[Publishing agent graphs](/graph-studio/publishing)**.

## Configuration

### Settings

- Version notes and change summaries
- Target environments (Dev, UAT, Prod)
- Tool and flow inclusion

### Environment-specific options

- API endpoints and credentials
- Feature flags
- Rate limits and quotas

<Note>
Do not hardcode secrets; use environment variables per environment.
</Note>

## Environments

- **Development** — rapid iteration
- **UAT** — stakeholder testing
- **Production** — live users

### Access controls

- Restrict publishing by role
- Separate credentials per environment

### Monitoring

Track performance and errors per environment in [Observability](/observability/overview).
