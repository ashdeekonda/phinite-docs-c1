---
title: Custom tools
description: Tool structure, test, publish, and attach to Agent Graph nodes.
---

**Custom tools** are Python handlers you author in Dev Studio for domain-specific logic.

## Tool contract

```python
def main(inputs, env_variables):
    return {
        "output": { ... },
        "captured_variables": { ... }
    }
```

| Argument | Source | Purpose |
| --- | --- | --- |
| `inputs` | Session variables (user, capture, API payload) | Runtime parameters |
| `env_variables` | [Env. variables](/configure/env-variables) (DEV / UAT / PROD) | Secrets and endpoints |

| Return key | Purpose |
| --- | --- |
| `output` | Primary result for the calling agent — prefer structured JSON |
| `captured_variables` | Values stored on the session for downstream steps |

<Warning>
  Never hardcode API keys. Use `env_variables.get("API_KEY")`.
</Warning>

### Example

```python
def main(inputs, env_variables):
    try:
        product_id = inputs.get("product_id")
        api_key = env_variables.get("INVENTORY_API_KEY")
        return {
            "output": {"stock": 42, "product_name": "Example"},
            "captured_variables": {"current_stock": 42}
        }
    except Exception as e:
        return {"output": {"error": str(e)}, "captured_variables": {}}
```

Define parameter types and descriptions in Dev Studio for validation and agent prompting.

## Test tools

1. Open the tool in **Dev Studio** → **Test** tab.
2. Enter realistic sample input JSON.
3. Choose **Dev**, **UAT**, or **Prod** for `env_variables`.
4. Review stdout, errors, and returned `output` / `captured_variables`.
5. Fix and re-test before **Publish**.

<Frame caption="Dev Studio Test panel">
  <img src="/images/test.png" alt="Dev Studio test panel" />
</Frame>

<Warning>
  Never put real secrets in sample inputs.
</Warning>

## Publish versions

1. **Draft** — edit handler and parameters.
2. **Test** — validate in Dev (and UAT per your process).
3. **Publish** — immutable version with release notes.
4. **Build** — pin when you build the Agent Graph.

Keep prior versions for rollback: re-attach in Graph Studio, **Save**, new **Build**, redeploy.

## Link to Graph Studio

Published tools attach on **Master Agent**, **Child Agent**, and **Tool** nodes.

1. Open [Graph Studio](/graph-studio/overview) → select a node → **Tools** tab.
2. **Add tool** → pick a **published** tool.
3. Map **input variables** from the session where shown.
4. **Save** the graph before **Build**.

<Frame caption="Agent node Tools tab">
  <img src="/images/enable-tools.png" alt="Tools tab with tool picker" />
</Frame>

See [Graph Studio — Agent configuration](/graph-studio/interface/node-library).

## Related

- [Methods](/devstudio/methods)
- [Tools & Dev Studio overview](/devstudio/overview)
- [Env. variables](/configure/env-variables)
