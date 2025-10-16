---
title: "Webhook Triggers"
description: "Start flows via external HTTP callbacks."
---

## Endpoint

<ParamField path="/api/triggers/webhook/:id" type="POST" required>
Receive webhook payloads to trigger flows.
</ParamField>

## Example request

<RequestExample>
```json cURL
{
  "event": "order.created",
  "data": {
    "orderId": "12345",
    "customerEmail": "user@example.com"
  }
}
```
</RequestExample>

<ResponseExample>
```json Success
{ "status": "accepted", "triggerId": "trig_abc" }
```
</ResponseExample>

<Warning>
Validate signatures and sanitize inputs before processing.
</Warning>
