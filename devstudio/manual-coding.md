---
title: "Manual Coding (Python)"
description: "Implement tool handlers, define parameters, and return structured results."
---

## Structure

- `handler`: main function with validated inputs
- `parameters`: input schema with types and defaults
- `returns`: output schema for downstream use

```python tool.py
from typing import TypedDict

class Params(TypedDict):
    to: str
    subject: str
    body: str

def handler(params: Params) -> dict:
    # send email via provider
    return {"status": "sent", "id": "msg_123"}
```

## Error handling

- Validate required parameters
- Raise descriptive exceptions
- Return consistent error shapes

## Testing

See [Testing Tools](/devstudio/testing-tools).
