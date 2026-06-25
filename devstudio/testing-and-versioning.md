---
title: "Testing and Versioning"
description: "Test tools, manage versions, and connect tools to agents."
---

## Testing tools

<Frame>
  <img src="/images/test.png" alt="testing-tools" />
</Frame>

### Steps

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

### Debugging

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

## Tool versioning

### Workflow

- Draft → Test → Publish → Use in flows

### Best practices

- Semantic versioning
- Clear version notes
- Test in Dev/UAT before Prod

### Rollbacks

- Keep previous versions available
- Document breaking changes

## Connecting tools to agents

### Steps

<Steps>
  <Step title="Select agent">
    <Frame>
      ![Select Agent](/images/select-agent.png)
    </Frame>

    Open the Agent node in Graph Studio.
  </Step>
  <Step title="Enable tools">
    <Frame>
      ![Enable Tools](/images/enable-tools.png)
    </Frame>

    Add tools in the Details/Tools tab.
  </Step>
  <Step title="Map variables">
    <Frame>
      <img
        alt="map variables"
        lightAlt="map variables"
        darkAlt="step-2"
        src="/images/map-variables.png"
      />
    </Frame>

    Map input variables to tool parameters.
  </Step>
</Steps>

<Tip>
  Use capture variables from tools for downstream logic.
</Tip>
