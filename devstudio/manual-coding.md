---
title: "Manual Coding (Python)"
description: "Implement custom tool handlers using Python when you need complete control over business logic, integrations, data processing, or external API interactions."
---

## Tool Structure

Every Python tool in Dev Studio follows a standard execution pattern with a single entrypoint:

```python
def main(inputs, env_variables):
```

### Parameters

#### inputs

A dictionary containing values from session variable (user\_variables, capture\_variables)

Example:

```python
{
    "urgency": "routine",
    "appointment_type": "telehealth"
}
```

#### env\_variables

A dictionary containing environment variables, secrets, API keys, and configuration values.

Example:

```python
{
    "API_TOKEN": "...",
    "DATABASE_URL": "..."
}
```

---

## Return Format

The script must return a dictionary with the following structure:

```python
return {
    "output": output_dict,
    "captured_variables": captured_variables
}
```

### output

The `output` object is returned directly to the agent and can be:

- Displayed to users
- Used in prompts
- Passed to downstream workflow steps
- Consumed by other agents

Example:

```python
{
    "appointments": [...]
}
```

### captured\_variables

Values inside `captured_variables` are automatically stored as session variables and become available throughout the workflow.

Example:

```python
{
    "slots_count": 3,
    "doctor_names": [
        "Dr. Sarah Mitchell",
        "Dr. Emily Watson"
    ]
}
```

These variables can be referenced by subsequent agents, tools, and workflow steps during the active session.

---

## Example Tool

The following example generates appointment slots based on user preferences:

```python
def main(inputs, env_variables):

    try:

        appointments = generate_slots(inputs)

        output_dict = {
            "appointments": appointments
        }

        captured_variables = {
            "slots_count": len(appointments)
        }

    except Exception as e:

        output_dict = {
            "error": str(e)
        }

        captured_variables = {}

    return {
        "output": output_dict,
        "captured_variables": captured_variables
    }
```

---

## Best Practices

### Keep Business Logic Separate

Move complex logic into helper functions rather than placing everything inside `main()`.

```python
def fetch_customer(customer_id):
    ...

def main(inputs, env_variables):
    customer = fetch_customer(
        inputs["customer_id"]
    )
```

### Handle Errors Gracefully

Always wrap execution in a `try/except` block and return meaningful error messages.

```python
try:
    ...
except Exception as e:
    output_dict = {
        "error": str(e)
    }
```

### Return Structured Data

Prefer dictionaries and arrays over plain text so downstream agents can reliably consume the output.

```python
{
    "customer": {
        "id": 123,
        "name": "John Smith"
    }
}
```

### Capture Reusable Values

Store frequently reused values in `captured_variables`.

```python
captured_variables = {
    "customer_id": customer["id"],
    "customer_name": customer["name"]
}
```

### Use Environment Variables for Secrets

Never hardcode API keys, credentials, or secrets in your code.

```python
api_key = env_variables.get(
    "API_TOKEN"
)
```

---

## Common Use Cases

- Calling external APIs
- Database queries
- Data transformation
- Custom business rules
- File processing
- Workflow orchestration
- AI model integrations
- Validation and enrichment pipelines

Manual Coding provides maximum flexibility and is ideal when built-in tools are insufficient or custom logic is required.

## Testing

See [Testing Tools](/devstudio/testing-tools).