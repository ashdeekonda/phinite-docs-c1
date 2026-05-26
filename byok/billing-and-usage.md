---
title: "Billing with BYOK"
description: "How using your own Model Keys affects Phinite platform billing and provider-side costs."
icon: "chart-line"
---

## Overview

When an agent node runs with a workspace Model Key (BYOK on in **Change model**), inference is billed by your **model provider**. Phinite records the run for observability but excludes most **platform-calculated model cost** for that usage.

When a node uses the **Phinite Key**, model inference cost is included in Phinite usage and billing according to your plan.

## Two cost layers

| Layer | Who bills you | What you pay |
| ----- | ------------- | ------------ |
| Model provider | Your cloud or API vendor | Tokens, images, video, audio per provider pricing |
| Phinite platform | Phinite subscription | Workspace features and non–own-key usage |

BYOK does not remove Phinite subscription charges. It shifts model inference spend to the account tied to your Model Key.

## How Phinite records BYOK runs

Usage events for inference can include `ownKey: true` when the run used customer-provided credentials.

For those events:

- Platform token and media **costs** are excluded from billed usage aggregation.
- **Volumes** such as sessions and events may still appear in observability.

See [Token usage](/observability/metrics/token-usage) and the [Billing dashboard](/observability/billing) when investigating usage.

## Plan availability

| Plan | BYOK (`features.byok`) |
| ---- | ---------------------- |
| Free (Basic) | No |
| Builder (Started) | No |
| Professional | Yes |
| Growth | Yes |
| Enterprise | Yes |

Plan comparison in the product lists **BYOK (Bring Your Own Keys)**. Confirm the organisation’s active subscription in Billing before enabling BYOK in production.

## Practices

- Use **Phinite Key** in development and dedicated Model Keys in production when accounts must stay separate.
- Set a clear workspace **Default Model** so new nodes do not unintentionally use platform credentials.
- Review provider billing consoles in addition to Phinite observability.

## Related

- [BYOK overview](/byok/overview)
- [Managing Model Keys](/byok/managing-model-keys)
- [Billing dashboard](/observability/billing)
