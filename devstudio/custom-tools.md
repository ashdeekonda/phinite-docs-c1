---
title: "Custom Tools"
description: "Build domain-specific functionality as reusable tools."
---

## Design

- Define parameters with clear types
- Implement robust error handling
- Return structured results for flows

## Example

```python inventory_tool.py
class Params(TypedDict):
    sku: str

def handler(params: Params):
    stock = lookup_inventory(params["sku"])  # your logic
    return {"in_stock": stock > 0, "stock": stock}
```

## Publishing

- Version tools with notes
- Test in Dev/UAT before Prod
- Monitor usage and errors
