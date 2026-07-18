---
title: "Testing Tools"
description: "Run tools with sample inputs across environments and debug failures in Dev Studio."
---

Use the Dev Studio **Test** panel to validate handlers before you **Publish** and pin versions on **Build**.

<Frame caption="Dev Studio Test panel — sample inputs and environment selector">
  <img src="/images/test.png" alt="Dev Studio tool test panel with JSON input" />
</Frame>

## Run a tool test

1. Open the tool in **Dev Studio** from workspace **Tools**.
2. Select the **Test** tab.
3. Enter realistic sample input JSON (session variables the tool expects in `inputs`).
4. Choose **Dev**, **UAT**, or **Prod** so `env_variables` resolve from the matching [environment](/configure/env-variables).
5. Run the test and review stdout, errors, and returned `output` / `captured_variables`.
6. Fix handler logic, re-test, then **Publish** when results match expectations.

## Example input

```json Example Input
{
  "to": "user@example.com",
  "subject": "Hello",
  "body": "Test"
}
```

<Warning>
  Never include real secrets in sample inputs. Use placeholder values; secrets belong in environment variables.
</Warning>

## Debugging failures

1. Confirm parameter names match your handler (`inputs.get("field")`).
2. Verify integration **connections** and env variable keys for the selected environment.
3. Cross-check runtime errors in [Session logs](/observability/logs) after attaching the tool to a graph test run.

## Related

- [Tool versioning](/devstudio/versioning)
- [Common build failures](/support/build-failures)
