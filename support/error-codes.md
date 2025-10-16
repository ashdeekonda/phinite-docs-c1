---
title: "Error Codes & Logs"
description: "Common error patterns, where to find logs, and how to resolve failures."
---

## Common errors

- 401 Unauthorized: Check token and roles
- 403 Forbidden: Insufficient permissions
- 404 Not Found: Resource missing or ID incorrect
- 422 Validation Error: Fix invalid inputs
- 500 Server Error: Check logs and retry

## Debugging steps

1. Reproduce with sample input
2. Check [Session Logs](/observability/logs)
3. Inspect tool/flow configuration
4. Verify environment and credentials

<Tip>
Include input, expected output, and actual error when reporting issues.
</Tip>
