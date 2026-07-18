---
title: "Session Logs & Analysis"
description: "Analyze execution traces, decisions, and variables to debug Agent Graph runs."
---

Session logs capture how an **Agent Graph** executed—node order, branching, tool calls, and captured variables.

<CardGroup cols={3}>
  <Card title="Timeline" icon="timeline" href="/observability/logs/timeline">
    Step-by-step trace with timestamps.
  </Card>
  <Card title="Decision joints" icon="code-branch" href="/observability/logs/decision-joints">
    Branching paths and exceptions.
  </Card>
  <Card title="Variables" icon="database" href="/observability/logs/variables">
    Captured session variables per step.
  </Card>
</CardGroup>

## Best practices

1. Filter by Agent Graph **build version** and environment before comparing runs.
2. Trace failures to specific tool calls and integration connections.
3. Export logs when you need audit trails outside the UI.

<Note>
  Logs describe runtime graph execution—not workspace [user roles](/user-management/user-roles) or Agent Card registry metadata.
</Note>

## Related

- [Filtering & Search](/observability/filtering)
- [Error codes & logs](/support/error-codes)
