---
title: Child Agent node
description: Specialized sub-agent with its own prompt, tools, and variables.
---

A **Child Agent** handles a delegated sub-task under a **Master Agent**. It has its own prompt, tools, RAG, and **Child Variables** tab.

## When to use

| Use Child Agent | Use Master Agent only |
| --- | --- |
| Distinct sub-task with separate prompt/tools | Single orchestration step is enough |
| Reusable specialist step in a large graph | Simple linear flows |

## Configure

1. Add a **Child Agent** node and connect it from a **Master Agent** (or upstream step).
2. Open the drawer → **Details** for the child task prompt.
3. Set **Tools**, **RAG**, and **Variables** (including **Child Variables** where shown).
4. **Save** the graph.

<Info>
  Child agents do not replace the Master Agent — the Master still orchestrates the overall run.
</Info>

## Related

- [Master Agent node](/graph-studio/nodes/master-node)
- [Node types](/graph-studio/nodes)
