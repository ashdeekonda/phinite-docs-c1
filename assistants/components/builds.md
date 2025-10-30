---
title: "Builds"
description: "Versioned artifacts for assistants and flows across environments."
---

## Overview
A **Build** is a versioned snapshot of an Assistant, including all its dependencies — flows, intents, triggers, and tools.

<Frame>
  <img src="/images/Build.png" alt="Descriptive alt text" />
</Frame>

Builds package flows and tools for deployment to environments. See [Builds & Environments](/builds/overview).



### Build Lifecycle

1. **Draft** — editable version.
2. **Build** — frozen snapshot for deployment.
3. **Release** — active and live.
4. **Rollback** — revert to a previous stable version.

<Steps>
  <Step title="Create Build">
    From the Assistant view, select **Build → Create Build**.
  </Step>
  <Step title="Select Environment">
    Choose Dev, UAT, or Prod.
  </Step>
  <Step title="Validate Dependencies">
    Ensure all flows, tools, and triggers are linked.
  </Step>
  <Step title="Deploy">
    Publish the build and monitor its performance.
  </Step>
</Steps>


## Best practices

- Version notes for every release
- Promote from Dev → UAT → Prod
- Use rollbacks when needed