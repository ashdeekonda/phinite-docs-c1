---
title: "API Reference"
description: "Authenticate and call Phinite APIs."
icon: terminal
---

## Authentication

<ParamField header="Authorization" type="string" required>
Bearer token for API authentication. Format: `Bearer YOUR_API_KEY`
</ParamField>

## Example: Trigger a webhook

<RequestExample>
```bash cURL
curl -X POST 'https://api.example.com/api/triggers/webhook/flow_123' \
  -H 'Authorization: Bearer YOUR_API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{"event":"order.created","data":{"orderId":"12345"}}'
```
</RequestExample>

<ResponseExample>
```json Success
{ "status": "accepted", "triggerId": "trig_abc" }
```
</ResponseExample>

<Warning>
Never expose API keys in client-side code.
</Warning>
