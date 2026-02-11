---
title: "Custom Tools"
description: "Build domain-specific functionality as reusable tools for your agents."
---

## Overview

Custom tools allow you to extend your agent's capabilities by writing Python functions that can interact with external APIs, process data, or perform specialized tasks.

## Tool Signature

Every custom tool must follow this standard signature:

```python
def main(inputs, env_variables):
    # Your tool logic here
    return {"output": output, "capture_variables": capture_variables}
```

### Parameters

<ParamField path="inputs" type="dict">
  Session variables passed to the tool. These can include:

  - Variables from agent capture variables
  - Variables returned by other tools in their `capture_variables` dictionary
  - Variables from the API payload that triggered the workflow

  **Access pattern:** `inputs.get("variable_name")`
</ParamField>

<ParamField path="env_variables" type="dict">
  Environment-specific secrets and configuration values defined in the Environment page, such as:

  - API keys
  - Authentication tokens
  - Database credentials

  **Access pattern:** `env_variables.get("API_KEY")`
</ParamField>

### Return Value

Your tool must return a dictionary with two keys:

```python
{
    "output": output,              # Used by the agent for decision-making
    "capture_variables": {}        # Stored in session for future use
}
```

<ResponseField name="output" type="any">
  The primary result of your tool's execution. The agent uses this value to understand what the tool accomplished.
</ResponseField>

<ResponseField name="capture_variables" type="dict">
  A dictionary of variables to store in the session. These can be accessed by other agents or tools later in the workflow.
</ResponseField>

---

## Creating a Custom Tool

### 1. Write Your Python Function

Navigate to the Custom Tools section and create a new tool with your Python code.

### 2. Add a Description

<Warning>
  The tool description is critical! The agent uses it to decide when to call your tool. Be specific about:

  - What the tool does
  - When it should be used
</Warning>

### 3. Example Tool

Here's a complete example of an inventory management tool:

```python inventory_tool.py
def main(inputs, env_variables):
    """
    Check inventory levels and return stock information.
    """
    # Get inputs
    product_id = inputs.get("product_id")
    api_key = env_variables.get("INVENTORY_API_KEY")
    
    # Your business logic
    import requests
    
    response = requests.get(
        f"https://api.inventory.com/products/{product_id}",
        headers={"Authorization": f"Bearer {api_key}"}
    )
    
    data = response.json()
    
    # Prepare output
    output = f"Product {product_id} has {data['stock']} units in stock"
    
    # Variables to save in session
    capture_variables = {
        "current_stock": data['stock'],
        "product_name": data['name'],
        "last_updated": data['updated_at']
    }
    
    return {
        "output": output,
        "capture_variables": capture_variables
    }
```

**Tool Description Example:**

```text
Checks the current inventory level for a given product ID. Returns current stock count 
and saves stock details.
```

## Best Practices

<AccordionGroup>
  <Accordion title="Environment Management">
    - **Dev**: Test new tools and changes
    - **UAT**: Validate with staging data
    - **Prod**: Deploy stable, tested versions

    Tools automatically use environment-specific variables based on the selected environment.
  </Accordion>
  <Accordion title="Version Control">
    - Add version numbers to your tools
    - Include release notes describing changes
    - Keep previous versions available for rollback
  </Accordion>
  <Accordion title="Error Handling">
    - Always validate inputs before processing
    - Use try-except blocks for external API calls
    - Return meaningful error messages in the output
    - Store errors in output dict or capture variables dict for debugging
  </Accordion>
  <Accordion title="Testing">
    - Test tools in Dev environment first
    - Validate with edge cases and invalid inputs
    - Monitor tool performance and errors in production
    - Check capture_variables are stored correctly
  </Accordion>
</AccordionGroup>

---

## Publishing Tool

<Steps>
  <Step title="Develop">
    Write and test your tool in the **Dev** environment. Will use env_variables values from dev.
  </Step>
  <Step title="Test">
    Track errors in console (catch error in output)
  </Step>
  <Step title="Publish">
    After thorough testing publish the version with version note.
  </Step>
</Steps>

<Tip>
  Use the monitoring dashboard to identify issues early and optimize tool performance.
</Tip>