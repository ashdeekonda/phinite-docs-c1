---
title: "AI Prompt Training"
description: "Train intents with examples and guidance for better recognition."
---

## Best practices

- Provide diverse examples that reflect real user language
- Include edge cases and negative examples
- Iterate using misclassifications from [Logs](/observability/logs)

## Example patterns

```markdown
User: "Where is my order?"
Intent: order_status

User: "I want to return this"
Intent: return_request
```

<Warning>
Avoid overfitting to narrow phrasing; prefer generalizable examples.
</Warning>
