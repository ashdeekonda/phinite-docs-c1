---
title: A2A endpoints and lifecycle
description: Hosted URL patterns, TEST vs LIVE, promotion, and authentication.
---

## What this is

Exposed agents receive a **hosted A2A URL** on the API gateway. URL shape depends on deployment status. **Push to Prod** promotes a TEST Agent Card version to LIVE.

## Hosted URLs

| Status | Pattern | Meaning |
| --- | --- | --- |
| **TEST** | `{gateway}/api/v1/ai/a2a/{flowId}/{registryId}` | Validation build tied to one registry row |
| **LIVE** | `{gateway}/api/v1/ai/a2a/{flowId}` | Production routing for the graph (one LIVE per graph per workspace) |

Use the URL copied from **Agent Registry** or **Agent Cards** — do not guess the host for your tenant.

Local dev may proxy under `http://localhost:3000/api/v1/ai/a2a/...`.

## Lifecycle

1. **Expose** → creates registry row with status **TEST** and Agent Card.
2. Validate against TEST URL.
3. **Push To Prod** → `PUT /api/v1/a2a-registry/{id}/promote-live`.
4. Previous LIVE for same graph demotes to **TEST**.

## Visibility and auth

| Visibility | Who can call |
| --- | --- |
| **Public** | Any client with a valid organisation **API key** |
| **Organisation** | Callers in the **same organisation** only |

Send the API key in the header your deployment documents (typically `X-API-Key`).

## Agent Card contract

Integrators consume from the Agent Card:

- Name, description, skills (input/output MIME modes)
- Discoverability tags
- Hosted URL (TEST vs LIVE pattern above)

Protocol reference: [A2A specification](https://a2a-protocol.org/latest/specification/).

## Related

- [Agent Card identity](/a2a/agent-card-identity)
- [Agent Registry](/a2a/registry)
- [Expose as A2A](/agents/expose-a2a)
- [Glossary](/reference/glossary-v2)
