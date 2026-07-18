---
title: Environments
description: DEV, UAT, and PROD for builds and variables.
---

Builds run in an **environment**. Env variables are scoped per DEV / UAT / PROD.

## Where

- Workspace → **Env. variables** — manage secrets and config columns for DEV, UAT, PROD.
- Studio → **Agent Builds** / **Deploy** — assign a build to an environment when deploying to a channel or trigger.

![Env. variables](/images/v2/builds/04-env-variables.png)

## Steps

1. Open **Env. variables**.
2. Add or edit variables; fill DEV / UAT / PROD values as needed.
3. When deploying a build, pick the environment that matches those credentials.

## Related

- [Builds](/agents/builds)
- [Deploy](/agents/deploy)
