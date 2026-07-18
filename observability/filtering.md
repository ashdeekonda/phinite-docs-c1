---
title: "Filtering & Search"
description: "Filter metrics and logs by time, Agent Graph, environment, and attributes."
---

Filters narrow observability data to the graph, environment, or channel you are debugging.

## Common filters

| Filter | Use |
| --- | --- |
| **Time range** | Incident windows, deploy comparisons |
| **Agent Graph** | Isolate a single graph's runs |
| **Environment** | DEV vs UAT vs PROD regressions |
| **Channel** | Webchat, Slack, telephony, API, etc. |
| **Build / version** | Compare behavior before and after a release |

## Tips

1. Save frequent filter combinations for on-call runbooks.
2. After deploy, filter by new build version to catch regressions early.
3. Pair filters with [timeline logs](/observability/logs/timeline) to trace failing tool calls.

<Note>
  Log and metric dimensions reference **Agent Graph** execution. [Agent Card](/agent-registry/overview) registry filters live under Agent Registry, not observability.
</Note>

## Related

- [Observability overview](/observability/overview)
- [Session logs](/observability/logs)
