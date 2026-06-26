---
title: "Build Lifecycle"
description: "From draft to deployed: how builds move through environments."
---

## Stages

1. Draft: agent graphs and tools under active development
2. Validated: passes checks and tests
3. Versioned: agent graph saved with **Save as Version** (release build optional from Graph Studio toolbar)
4. Deployed: build assigned and running in target environment via **Assign Build**

## Promotion

- Promote Dev → UAT → Prod with **Assign Build** on the Deploy section
- Require approvals for Prod
- Maintain rollback plans
