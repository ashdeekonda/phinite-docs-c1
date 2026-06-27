---
title: "Expose your agent graph as an A2A agent"
description: "Register a published agent graph in the Agent Registry using the Expose as External Agent wizard and attach an Agent Card."
---

## Prerequisites

Before you expose an agent graph:

- **Publish** at least one version of the agent graph. See [**Agent Graph publishing**](/graph-studio/publishing).
- Hold **Developer** role or higher for Graph Studio save/publish actions.
- Have permission to call registry APIs (`assistants.flows:create` via the gateway **`POST /a2a-registry`**).
- Run in a **local or dev** environment where **Configure Agent** is visible in Graph Studio (see [**Overview — Access and environment**](/agent-registry/overview#access-and-environment)).

Associated **tools** referenced by the graph must be **published** before you can select them in step 1 of the wizard.

## Open the expose flow

1. Open **Graph Studio** for your project.
2. Select the agent graph you want to expose.
3. In the canvas header, click **Configure Agent** (dev environments only).
4. In the **Expose as Agent** modal, review any existing test/live builds and hosted URLs.
5. Click **Create New Build** to open the **Expose as External Agent** wizard.

<Frame>
  ![Expose As Agent](/images/Expose-as-agent.png)
</Frame>

The modal explains that publishing an Agent Card enables the graph as a **hosted agent** callable via the **A2A protocol**. Use **See Agent builds** to jump to [**Agent Cards**](/agent-registry/agent-cards) for the project.

## Wizard steps

The wizard has three steps. Step labels in the UI:

| Step | Label | Purpose |
| --- | --- | --- |
| 1 | **Agent Build Config** | Pick agent graph version and published tools |
| 2 | **Additional Config** | Optional export of tools/variables to the build |
| 3 | **Configure the Agent card** | Agent Card identity, skills, tags, visibility |

Primary actions: **Next** (steps 1–2), **Attach Agent Card** (step 3).

### Step 1 — Agent Build Config

<Frame>
  ![Expose Agent Step 1](/images/Expose-agent-step-1.png)
</Frame>

**Confirm the Agent Config:**

- **Agent Graph** accordion — select the flow version to register (name, version number, version notes, timestamp).
- **Tools Associated** accordion — select published tool versions linked to the graph. Unpublished tools show a **Publish** action inline.

Validation requires a selected graph version. If tools exist on the graph, at least one **published** tool must be selected.

### Step 2 — Additional Config

**Variables and Secrets:**

- Toggle **Export to build** to include predefined tools, MCP tools, or environment variables in the registry build.
- When enabled, use tabs **Predefined**, **MCP**, and **Env** and search **Search tools and variables...**
- For each exported row, provide a **description** (required).

When export is disabled, the step shows: _Enable "Export value to build" to configure additional tools and variables._

### Step 3 — Configure the Agent card

<Frame>
  ![Expose Agent Step 3](/images/expose-agent-step-3.png)
</Frame>

**Agent Card is the identity of your agent on the Internet:**

| Field | Notes |
| --- | --- |
| **Agent Name** | Read-only; derived from the agent graph name |
| **Agent Description** | Editable summary for catalog and A2A clients |
| **Skills** | Add skills with unique name, description, **Input Modes**, and **Output Modes** (MIME types) |
| **Discoverability Tags** | Tags help agents appear in search and Discovery filters |
| **Visibility & access** | **Public** — discoverable by any A2A-compatible agent or user with a valid API key. **Organisation** — visible only within your organisation |
| **Auth Schemes** | Platform default: use your Phinite organization **API key** |
| **Refine Card** | Optional AI refinement (`refine_prompt_for: "a2a"`) to improve description and skills |

Click **Attach Agent Card** to submit. The UI calls **`POST /a2a-registry?workspaceid={workspaceId}`** with the wizard payload (`agent_card`, `flowid`, `flow_version`, `assistantid`, tools, and optional export config).

## After registration

<Frame>
  ![After Agent Registration](/images/after-agent-registration.png)
</Frame>

On success:

- Note the **Agent Registry ID** and **hosted A2A URL** (test builds use the registry ID in the path—see [**Endpoints & lifecycle**](/agent-registry/endpoints-and-lifecycle)).
- The success message indicates the build is available to **Test**.
- Click **Go to Agent Registry** to open the workspace catalog.

New registrations start with deployment status **`test`**. Promote to **`live`** from [**Agent Cards**](/agent-registry/agent-cards) when you are ready for production routing.

## Related pages

<CardGroup cols={2}>
  <Card title="Endpoints & lifecycle" icon="plug" href="/agent-registry/endpoints-and-lifecycle">
    Test vs live URL patterns and promotion.
  </Card>

  <Card title="Browse the catalog" icon="layout-grid" href="/agent-registry/catalog">
    Find and inspect registered agents.
  </Card>
</CardGroup>