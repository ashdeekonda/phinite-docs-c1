---
title: "API Reference"
description: "Authenticate and call Phinite APIs."
icon: terminal
---

## Authentication

<ParamField header="Authorization" type="string" required>
Bearer token or session cookie for workspace APIs. Format: `Bearer YOUR_API_KEY`
</ParamField>

Some AI-core routes (A2A agent invoke and agent-card discovery) accept an organisation **API key** in the `X-API-Key` header instead. See **[A2A endpoints & lifecycle](/agent-registry/endpoints-and-lifecycle)**.

## Trigger an autonomous assistant

Autonomous assistants expose event triggers on the API gateway:

```
POST https://app.phinite.ai/api/v1/ai/trigger/{workspace_id}/{trigger_id}/{environment}
```

Replace `{environment}` with `dev`, `uat`, or `prod`. Full request shapes, headers, and response codes: **[Trigger API guide](/triggers-intents/triggers/api-guide)**.

<RequestExample>
```bash cURL
curl -X POST 'https://app.phinite.ai/api/v1/ai/trigger/{workspace_id}/{trigger_id}/prod' \
  -H 'Authorization: Bearer YOUR_API_KEY' \
  -H 'Content-Type: application/json' \
  -d '{"event":"order.created","data":{"orderId":"12345"}}'
```
</RequestExample>

## Agent Registry (A2A)

Hosted agents are invoked at `POST /api/v1/ai/a2a/agents/{registryId}` (and agent-card discovery at `GET .../agents/{registryId}/.well-known/agent-card.json`). Test vs live URL patterns and promotion: **[Endpoints & lifecycle](/agent-registry/endpoints-and-lifecycle)**.

## OpenAPI

Interactive OpenAPI documentation is served by api-server at **`/api-docs`** on your gateway host (for example `https://app.phinite.ai/api-docs`).

<Warning>
Never expose API keys in client-side code.
</Warning>
