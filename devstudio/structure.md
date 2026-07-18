---
title: "Tool Structure & Parameters"
description: "Define input schemas, validation, return types, and captured variables for Dev Studio tools."
---

Every custom tool shares the same contract: a `main(inputs, env_variables)` entrypoint and a structured return value agents consume at runtime.

## Entrypoint

```python
def main(inputs, env_variables):
    return {
        "output": { ... },
        "captured_variables": { ... }
    }
```

| Argument | Source | Purpose |
| --- | --- | --- |
| `inputs` | Session variables (user, capture, API payload) | Runtime parameters from the Agent Graph |
| `env_variables` | Workspace env config (DEV / UAT / PROD) | Secrets, API keys, endpoints |

<ParamField path="inputs" type="dict">
  Values passed from the active session. Access with `inputs.get("name")`.
</ParamField>

<ParamField path="env_variables" type="dict">
  Environment-scoped secrets from [Env. variables](/configure/env-variables). Access with `env_variables.get("API_KEY")`.
</ParamField>

## Return shape

<ResponseField name="output" type="dict | str">
  Primary result returned to the calling agent node—used in prompts and downstream logic. Prefer structured JSON over free text.
</ResponseField>

<ResponseField name="captured_variables" type="dict">
  Key-value pairs stored on the session for later nodes and tools. Also written to [variable capture logs](/observability/logs/variables).
</ResponseField>

<Note>
  Some legacy examples use `capture_variables` (singular *capture*). New tools should use `captured_variables` consistently.
</Note>

## Parameter schema (UI)

When you define tool parameters in Dev Studio:

- Mark required fields so the runtime rejects missing inputs early.
- Set types (`string`, `number`, `boolean`, `object`, `array`) for validation and agent prompting.
- Add descriptions—the agent reads them when choosing arguments.

## Validation & errors

1. Validate required `inputs` before external calls.
2. Wrap risky operations in `try/except` and return `{ "error": "..." }` inside `output` when appropriate.
3. Keep error shapes consistent so agents can retry or escalate gracefully.

## Related

- [Manual coding (Python)](/devstudio/manual-coding)
- [Custom tools](/devstudio/custom-tools)
