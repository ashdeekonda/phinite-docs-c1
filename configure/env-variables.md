---
title: Env. variables
description: DEV, UAT, and PROD environment variables for builds and integrations.
---

**Env. variables** store secrets and config per **environment** (DEV, UAT, PROD). **Agent Builds** and integrations read these at runtime — values are not stored on the **Agent Graph** canvas.

<Note>
  Sensitive values display masked in the table. Tools and channels reference env keys by name — keep naming consistent across DEV → PROD promotion. Permission: `workspace.sidebar.environment`.
</Note>

## Where in the product

| Surface | Path |
| --- | --- |
| Workspace sidebar | **Env. variables** |
| URL | `/{org}/workspace/{workspaceId}/environment` |
| Build assign | Graph Studio → **Deploy** / **Agent Builds** → assign build to environment |

<Frame caption="Env. variables — DEV, UAT, PROD columns">
  <img src="/images/v2/builds/04-env-variables.png" alt="Environment variables table" />
</Frame>

## Configure variables

1. Open **Env. variables** from the workspace sidebar.
2. Click **New Environment** or edit an existing variable row.
3. Enter **Variable Name** and values for **DEV**, **UAT**, and **PROD** as needed.
4. Save each row.
5. When deploying, assign the **Agent Build** to the environment whose values you configured ([Builds & environments](/builds/environments)).

<Tip>
  Keep variable **names** consistent across DEV → PROD. Only the **values** should change (API keys, base URLs, feature flags).
</Tip>

## Related

<CardGroup cols={2}>
  <Card title="Configuration overview" icon="sliders" href="/configure/overview">
    All configuration layers in one place.
  </Card>
  <Card title="Build export" icon="file-export" href="/configure/build-export">
    Pin tools, MCP, and env into immutable builds.
  </Card>
  <Card title="Build environments" icon="layer-group" href="/builds/environments">
    Assign builds to DEV, UAT, and PROD.
  </Card>
  <Card title="Integrations" icon="plug" href="/configure/integrations">
    Channels, triggers, and predefined tools.
  </Card>
</CardGroup>
