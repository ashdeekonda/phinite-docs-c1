---
title: "Tool Types"
description: "Custom tools, system tools, and prebuilt integrations for Agent Graphs."
---

Tools fall into three categories. All must be **published** (except system tools) before an Agent Build pins them at **Build** time.

<CardGroup cols={2}>
  <Card title="Custom tools" icon="screwdriver-wrench" href="/devstudio/custom-tools">
    Python handlers you author in Dev Studio for domain-specific logic.
  </Card>
  <Card title="System tools" icon="gears" href="/devstudio/system-tool">
    Built-in orchestration helpers available to every agent node (RAG, Finish, End Graph, Insight).
  </Card>
  <Card title="Predefined tools" icon="plug" href="/devstudio/prebuilt-tools">
    Connect SaaS APIs once; full vendor catalog in Integrations Hub.
  </Card>
  <Card title="Link to nodes" icon="diagram-project" type="note" href="/devstudio/linking-tools">
    Attach published tools on agent nodes in Graph Studio.
  </Card>
</CardGroup>

## Quick comparison

| Type | Authored in | Versioned | Typical use |
| --- | --- | --- | --- |
| **Custom** | Dev Studio | Yes | Business APIs, data transforms, approvals |
| **System** | Platform | N/A | Flow control, RAG retrieval, user status updates |
| **Prebuilt** | Integration connection + subtool enablement | Per connection | SaaS connectors with OAuth or API tokens |

<Note>
  **Integration Tools** configured under workspace [Integrations](/configure/integrations) appear alongside Dev Studio tools when linking to agent nodes.
</Note>

## Related

- [Ways to build tools](/devstudio/methods)
- [Tool structure & parameters](/devstudio/structure)
