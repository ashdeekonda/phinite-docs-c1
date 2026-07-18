---
title: Env. variables
description: DEV, UAT, and PROD environment variables for builds and integrations.
---

## What this is

**Env. variables** store secrets and config values per **environment** (DEV, UAT, PROD). Builds and integrations read these values at runtime — they are not embedded in the graph canvas.

## Where in the product

| Surface | Path |
| --- | --- |
| Workspace sidebar | **Env. variables** |
| URL | `/{org}/workspace/{workspaceId}/environment` |
| Build assign | Studio → **Deploy** / Agent Builds → assign build to environment |

![Env. variables](/images/v2/builds/04-env-variables.png)

## Steps

1. Open **Env. variables** from the workspace sidebar.
2. Click **New Environment** or edit an existing variable row.
3. Enter the **Variable Name** and values for **DEV**, **UAT**, and **PROD** columns as needed.
4. Save each row.
5. When deploying a build, assign it to the environment whose values you configured ([Environments](/agents/environments)).

## Notes

- Sensitive values display masked in the table.
- Tools and channels reference env keys by name; keep naming consistent across DEV → PROD promotion.
- Permissions: `workspace.sidebar.environment`.

## Related

- [Configuration overview](/configure/overview)
- [Integrations](/configure/integrations)
- [Build export](/configure/build-export)
- [Builds](/agents/builds)
