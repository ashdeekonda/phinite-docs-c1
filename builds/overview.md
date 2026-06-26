---
title: "Builds & Environments Overview"
description: "Manage build lifecycle and deploy agent graphs and tools across environments."
---

## What is a build?

<Frame>
  ![Build](/images/Build.png)
</Frame>

A build is a versioned package of your agent graphs and tools prepared for deployment to environments (Dev, UAT, Prod). In the assistant **Deploy** section, use **Create Build** to package a **Save as Version** snapshot of an agent graph and its published tools, then **Assign Build** to map that build to Dev, UAT, or Production.

From **Graph Studio**, use the toolbar actions **Create a release build** or **Test a release build** after you save a new agent graph version. Release builds feed the same Deploy workflow as builds created on the Deploy page.

## Lifecycle

- Draft → Validated → Saved as Version → Deployed

## Related

- [Build Lifecycle](/builds/lifecycle)
- [Publishing Agent Graphs & Tools](/builds/publishing)
- [Environment Types](/builds/environments)
- [Agent Cards & builds](/agent-registry/agent-cards) — promote exposed A2A agents from test to live