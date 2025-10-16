---
title: "Tool Block"
description: "Calls external APIs or tools during the flow."
---

## Configuration

- **Tool selection**: choose the tool or sub-tool to invoke
- **Inputs**: map variables to tool parameters
- **Outputs**: expose results for downstream steps

<Note>
Implemented as the `api` node type in `src/components/nodes/api/`. Tool metadata is sourced from your workspace tools.
</Note>
