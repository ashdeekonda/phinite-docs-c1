---
title: "Tool Types"
description: "Custom tools and pre-built integrations."
---

## Types

- **Custom Tools**: Purpose-built logic for your business
- **Pre-built Integrations**: Gmail, Sheets, Jira/Zendesk, and more

See [Pre-built Integrations](/devstudio/prebuilt-tools).

## Custom tools

### Overview

Custom tools allow you to extend your agent's capabilities by writing Python functions that can interact with external APIs, process data, or perform specialized tasks.

### Tool Signature

Every custom tool must follow this standard signature:

```python
def main(inputs, env_variables):
    # Your tool logic here
    return {"output": output, "capture_variables": capture_variables}
```

#### Parameters

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

#### Return Value

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

### Creating a Custom Tool

#### 1. Write Your Python Function

Navigate to the Custom Tools section and create a new tool with your Python code.

#### 2. Add a Description

<Warning>
  The tool description is critical! The agent uses it to decide when to call your tool. Be specific about:

  - What the tool does
  - When it should be used
</Warning>

#### 3. Example Tool

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

### Best Practices

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

### Publishing Tool

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

## System tools

### Overview

System tools are automatically available to every agent and don't require custom configuration. These tools help agents orchestrate workflows, retrieve information, and provide better user experiences.

### Available System Tools

<CardGroup cols={2}>
  <Card title="RAG Tool" icon="database">
    Retrieve information from datasources
  </Card>
  <Card title="Finish Tool" icon="flag-checkered">
    Complete current agent task
  </Card>
  <Card title="End Agent Graph Tool" icon="circle-stop">
    Terminate the entire workflow
  </Card>
  <Card title="Agent Graph Insight Tool" icon="comment-dots">
    Provide status updates to users
  </Card>
</CardGroup>

### RAG Tool

#### Purpose

Retrieves relevant information from datasources attached to the agent block.

#### Usage

Simply mention in your agent prompt when the tool should be called:

```text Agent Prompt Example
When the user asks about product specifications or documentation, 
use the RAGTool to search the knowledge base for relevant information.
```

The agent will automatically access the datasources you've attached to the agent block and retrieve the most relevant information.

<Note>
  Make sure to attach your datasources to the agent block before referencing the RAG Tool.
</Note>

### Finish Tool

#### Purpose

Signals that the current agent has completed its task and no further action is needed from this agent block.

#### Usage

Instruct the agent to call this tool when its specific objective is complete:

```text Agent Prompt Example
Once you have successfully collected the user's name, email, and phone number, 
call the FinishTool to complete this step.
```

#### When to Use

- Agent has gathered all required information
- Task objective has been accomplished
- Ready to pass control to the next agent or step

<Tip>
  If your agent is finishing prematurely, explicitly define the conditions for calling FinishTool in your prompt.
</Tip>

### End Agent Graph Tool

#### Purpose

Terminates the entire workflow immediately, regardless of remaining steps.

#### Usage

Use this tool when the entire flow should stop:

```text Agent Prompt Example
If the user explicitly says "bye" or "stop", call the EndFlowTool 
to immediately terminate the entire workflow.
```

#### When to Use

- User requests to cancel the process
- Critical error that prevents continuation
- Agent Graph objective has been fully completed
- User wants to exit the conversation

<Warning>
  This tool stops the **entire workflow**, not just the current agent. Use FinishTool if you only want to complete the current agent's task.
</Warning>

### Agent Graph Insight Tool

#### Purpose

Provides real-time status updates to users during tool execution, making conversations feel more natural and interactive.

#### Usage

The agent automatically uses this tool to inform users when processing is happening:

```text Agent Prompt Example
When calling any external tool or API, use the FlowInsightTool to let 
the user know you're working on their request.
```

#### Example Responses

<CodeGroup>

```text Checking Account
"One moment, I'm looking into your account details..."
```


```text Processing Payment
"Please wait while I process your payment..."
```


```text Searching Database
"Let me search our database for that information..."
```


```text Calling API
"I'm checking with our system now..."
```

</CodeGroup>

#### Benefits

- Reduces user anxiety during processing time
- Makes the conversation feel more human
- Provides transparency about what's happening
- Improves overall user experience

---

### Best Practices

<AccordionGroup>
  <Accordion title="Explicit Tool Calling Instructions">
    If your agent is calling system tools at the wrong time:

    ✅ **Do:** Be explicit about when to call each tool

    ```text
    Call FinishTool ONLY after you have:
    1. Verified the user's identity
    2. Processed their request
    3. Confirmed the outcome with the user
    ```

    ❌ **Don't:** Leave tool calling conditions ambiguous

    ```text
    Use FinishTool when done.
    ```
  </Accordion>
  <Accordion title="Preventing Premature Exits">
    If agents are ending flows too early:

    - Explicitly list all required steps before calling FinishTool/EndFlowTool
    - Add validation checkpoints in your prompt
    - Use conditional statements for tool calling

    ```text Example
    Before calling FinishTool, ensure:
    - User has provided all required information
    - Information has been validated
    - Confirmation message has been sent to user
    ```
  </Accordion>
  <Accordion title="RAG Tool Optimization">
    - Attach only relevant datasources to each agent
    - Provide clear instructions on when to search
    - Test retrieval quality with sample queries
    - Update datasources regularly for accuracy
  </Accordion>
  <Accordion title="Agent Graph Insight Messages">
    Keep insight messages:

    - Brief and conversational
    - Relevant to the action being performed
    - Professional but friendly
    - Transparent about what's happening
  </Accordion>
</AccordionGroup>

---

### Troubleshooting

<ResponseField name="Agent ends flow prematurely">
  Add explicit conditions in your prompt for when to call FinishTool or EndFlowTool. List all required steps that must be completed first.
</ResponseField>

<ResponseField name="RAG Tool not finding information">
  - Verify datasources are properly attached to the agent block
  - Check that datasources contain the relevant information
  - Review the quality and format of your datasource content
</ResponseField>

<ResponseField name="Agent Graph Insight messages not appearing">
  - Ensure the agent prompt mentions using FlowInsightTool
  - Verify the conversational flow is configured correctly
  - Check that the tool is being called before long-running operations
</ResponseField>

## Tool structure & parameters

### Parameters

<ParamField body="param" type="string" required>Describe expected parameter</ParamField>

### Validation

- Required fields enforced
- Types checked at runtime
- Descriptive error messages

### Returns

- Structured objects for capture variables
- Consistent error shape for failures
