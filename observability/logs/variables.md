---
title: "Variable Capture Logs"
description: "Inspect captured variables and data flow across Agent Graph nodes."
---

Variable capture logs show what each tool and agent node wrote to the session—essential for debugging data handoffs.

## Use cases

1. Verify extraction prompts populate expected fields.
2. Debug missing or malformed values before downstream nodes run.
3. Confirm tool `captured_variables` match [Dev Studio structure](/devstudio/structure).

<Note>
  Captured variables are **runtime session state**, not workspace [env variables](/configure/env-variables) or Agent Card metadata.
</Note>

## Related

- [Agent node variables](/graph-studio/agent-node/variables)
- [Timeline view](/observability/logs/timeline)
