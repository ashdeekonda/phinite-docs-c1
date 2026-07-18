---
title: "CustomApiTools"
description: "Generic HTTP client for private or non-standard APIs from Agent Graph tools."
icon: "code"
---

**CustomApiTools** calls arbitrary HTTP endpoints when no dedicated prebuilt connector exists. Use it for internal microservices or legacy REST APIs.

<Card title="Predefined tools hub" icon="plug" href="/devstudio/prebuilt-tools">
  Connection fields shared across prebuilt tools.
</Card>

## Configuration

| Field | Required | Notes |
| --- | --- | --- |
| `base_url` | Yes | Root URL (for example `https://api.example.com/v1`) |
| `username` / `password` | No | Basic auth |
| `api_key` | No | Header or query API key |
| `headers` | No | Default HTTP headers (object) |
| `timeout` | No | Seconds to wait per request |

## Setup

1. Add **CustomApiTools** on an agent node and create a connection with at least `base_url`.
2. Store sensitive values in [env variables](/configure/env-variables) when possible; reference them from tool code for signing logic.
3. Enable `make_request` and document allowed methods/paths in the agent prompt.
4. Test a read-only `GET` before enabling mutating verbs in production graphs.

## Subtools

- `make_request` — `method`, `path`, optional `query`, `body`, `headers`, `auth`, `timeout`

<Note>
  Validate user-supplied paths to avoid SSRF. Prefer server-side gateways for HMAC or signed requests instead of embedding signing secrets in prompts.
</Note>
