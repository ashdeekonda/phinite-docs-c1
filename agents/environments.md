---
title: Environments
description: Quick reference — DEV, UAT, and PROD for Agent Builds and env variables.
---

**Agent Builds** run in an **environment**. **Env. variables** are scoped per **DEV**, **UAT**, and **PROD** column on the workspace **Env. variables** page.

<Note>
  Full environment documentation: **[Build environments](/builds/environments)**. Env. variable setup: **[Env. variables](/configure/env-variables)**.
</Note>

## Where environments appear

| Surface | Purpose |
| --- | --- |
| Workspace → **Env. variables** | Secrets and config per DEV / UAT / PROD |
| Studio → **Agent Builds** / **Deploy** | Assign a build to an environment for channels and triggers |
| Channel / trigger webhooks | Separate URLs per environment (Development, UAT, Production) |

<Frame caption="Env. variables — DEV, UAT, and PROD columns">
  <img src="/images/v2/builds/04-env-variables.png" alt="Environment variables table with DEV UAT PROD columns" />
</Frame>

## Quick workflow

1. Configure variables in **Env. variables** ([configure guide](/configure/env-variables)).
2. Create an **Agent Build** ([Builds overview](/builds/overview)).
3. Assign the build to **DEV** first; test via channel or trigger.
4. Promote assignment to **UAT** / **PROD** when validated.

## Related

- [Build environments](/builds/environments)
- [Env. variables](/configure/env-variables)
- [Deploy](/agents/deploy)
