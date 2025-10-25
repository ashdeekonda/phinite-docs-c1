---
title: "Testing Tools"
description: "Run tools with sample inputs across environments and debug failures."
---

## Steps

<Frame>
  <img src="/images/test.png" alt="testing-tools" />
</Frame>

<Steps>
  <Step title="Open Test panel">
    Open the tool and select the Test tab.
  </Step>
  <Step title="Provide input">
    Enter realistic sample input JSON.
  </Step>
  <Step title="Run in environment">
    Choose Dev/UAT/Prod and run. Review logs for errors.
  </Step>
</Steps>

## Debugging

```json Example Input
{
  "to": "user@example.com",
  "subject": "Hello",
  "body": "Test"
}
```

<Warning>
  Never include real secrets in sample inputs.
</Warning>