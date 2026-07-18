---
title: Builds
description: Summary — freeze an Agent Graph and tool versions into a deployable Agent Build.
---

An **Agent Build** is an immutable snapshot of your **Agent Graph** and pinned **tool** versions. Builds are required before **Deploy**, environment assignment, and A2A exposure.

<Note>
  Canonical documentation lives under **[Builds & Environments](/builds/overview)**. This page is a quick reference from the Agent Graphs section of the nav.
</Note>

## Create an Agent Build

1. In Graph Studio, **Save** the Agent Graph.
2. Click **Build** on the toolbar.
3. Wait while Phinite validates the graph and packages tool versions.
4. Add a **Description** on the **Build Agent** form.
5. Confirm **AGENT GRAPH** version and **TOOLS** — click **Publish** on any unpublished tool.
6. Click **Create Build**.

Builds appear under Studio → **Agent Builds** in the graph assets sidebar.

<Frame caption="Build Agent form — graph version and tool pinning">
  <img src="/images/v2/builds/03-build-form.png" alt="Build Agent dialog with graph and tools" />
</Frame>

## What happens next

| Step | Doc |
| --- | --- |
| Assign **DEV / UAT / PROD** | [Build environments](/builds/environments) |
| **Deploy** to channel or trigger | [Deploy](/agents/deploy) |
| **Expose as A2A** | [Expose your flow](/agent-registry/expose-your-flow) |

## Full reference

<CardGroup cols={2}>
  <Card title="Builds overview" icon="box" href="/builds/overview">
    Hub for lifecycle, publishing, and configuration.
  </Card>
  <Card title="Build lifecycle" icon="arrow-right-arrow-left" href="/builds/lifecycle">
    Draft → validated build → deployed in an environment.
  </Card>
  <Card title="Build configuration" icon="gear" href="/builds/configuration">
    Version pins, export, and env-specific options.
  </Card>
  <Card title="Publishing" icon="upload" href="/builds/publishing">
    Publish tools and promote builds safely.
  </Card>
</CardGroup>
