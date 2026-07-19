---
title: Model Keys
description: BYOK provider keys and model selection for agent nodes.
---

**Model Keys** let you bring your own provider credentials (BYOK) or use the platform **Phinite Key**. **Master Agent** and **Child Agent** nodes select which model and key to use for LLM calls on the **Agent Graph**.

<Note>
  **Save** the Agent Graph before **Build** after changing model or key on a node. Permission: `workspace.sidebar.byok`.
</Note>

## Where in the product

| Surface | Path |
| --- | --- |
| Workspace **Keys** pocket | **Model Keys** |
| URL | `/{org}/workspace/{workspaceId}/model-key` |
| Per-node model | Graph Studio → agent node drawer → model / provider fields |

<Frame caption="Model Keys — BYOK providers and Phinite Key">
  <img src="/images/v2/workspace/01-model-keys.png" alt="Model Keys workspace page" />
</Frame>

## Workspace keys

1. Open **Keys** in the workspace sidebar (bottom section).
2. Click **Model Keys**.
3. Add a provider key or use the default **Phinite Key** card.
4. Set which key is default for the workspace if prompted.

## Use on an agent node

1. Open **Graph Studio** and select a **Master Agent** or **Child Agent** node.
2. In the node drawer, choose **model** and provider settings.
3. Pick a key that matches your BYOK setup.
4. **Save** the **Agent Graph** before **Build**.

<Info>
  The **Phinite Key** uses platform-managed credentials. BYOK keys are stored per workspace and never embedded in the graph JSON.
</Info>

## Related

<CardGroup cols={2}>
  <Card title="Agent node" icon="robot" href="/graph-studio/interface/node-library">
    Drawer fields for prompts, tools, and model.
  </Card>
  <Card title="Graph Studio overview" icon="diagram-project" href="/graph-studio/overview">
    Design Agent Graphs on the canvas.
  </Card>
  <Card title="Builds overview" icon="box" href="/builds/overview">
    Freeze graph and tool versions into Agent Builds.
  </Card>
  <Card title="Configuration overview" icon="sliders" href="/configure/overview">
    All configuration layers in one place.
  </Card>
</CardGroup>
