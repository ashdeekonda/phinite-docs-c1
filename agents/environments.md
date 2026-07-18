---
title: Environments
description: DEV, UAT, and PROD for builds and variables.
---

Builds run in an **environment**. Env variables are scoped per DEV / UAT / PROD.

For full steps and the env variables table, see **[Env. variables](/configure/env-variables)**.

## Where

- Workspace → **Env. variables** — manage secrets and config columns for DEV, UAT, PROD.
- Studio → **Agent Builds** / **Deploy** — assign a build to an environment when deploying to a channel or trigger.

![Env. variables](/images/v2/builds/04-env-variables.png)

## Quick steps

1. Configure variables in **Env. variables**.
2. Create a **Build**.
3. Assign the build to **DEV** first; test via channel or trigger.
4. Promote assignment to **UAT** / **PROD** when validated.

## Related

- [Env. variables](/configure/env-variables)
- [Builds](/agents/builds)
- [Deploy](/agents/deploy)
