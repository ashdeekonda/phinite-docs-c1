---
title: "Billing with BYOK"
description: "How Model Keys affect Phinite platform billing and what your model provider charges separately."
icon: "chart-line"
---

When an agent node runs with a workspace Model Key, your **model provider** charges for that inference—not Phinite. When a node uses the **Phinite Key**, inference cost is included in your Phinite subscription.

BYOK does not replace your Phinite subscription. It redirects model inference spend to the provider account tied to the key you selected.

## Two billing layers

Every BYOK-enabled workspace has two separate invoices to monitor:

1. **Model provider** — Azure, Google Cloud, Anthropic, or others. Charges for tokens, images, video, and audio at vendor rates. Review this in your cloud console.
2. **Phinite** — Your subscription plus any usage not attributed to a workspace key. Review this in the Phinite **Billing** dashboard.

![Billing or Token usage view for cross-referencing BYOK runs](/images/byok/billing-usage-context.png)

## How Phinite records own-key runs

When inference uses your Model Key, usage events can carry an own-key flag.

- Platform **token and media cost** is typically excluded from billed aggregation.
- **Session and event counts** may still appear in observability for operations and debugging.

Review usage across these pages together:

- [Token usage](/observability/metrics/token-usage)
- [Billing dashboard](/observability/billing)
- [Usage metrics](/observability/usage-metrics)

<Tip>
In runbooks, note which agent graphs use BYOK and which use the Phinite Key. It makes usage dashboards easier to interpret during releases and incidents.
</Tip>

## Plan availability

BYOK is available on Professional, Growth, and Enterprise. It is not available on Free or Builder.

| Plan | BYOK available |
| --- | --- |
| Free (Basic) | No |
| Builder (Started) | No |
| Professional | Yes |
| Growth | Yes |
| Enterprise | Yes |

Confirm the active plan under organisation **Billing** before you depend on BYOK in production.

## Practices

- Use **Phinite Key** in development and test workspaces. Use named provider keys in production where accounts must stay separate.
- Set **Default Model** deliberately on each workspace so new nodes do not pick up the wrong key mode by accident.
- Reconcile your provider billing consoles with Phinite observability at least monthly.

## Related pages

<CardGroup cols={2}>
<Card title="BYOK overview" href="/byok-v2/overview" icon="book-open">
End-to-end workflow and prerequisites.
</Card>
<Card title="API & permissions" href="/byok-v2/api-and-permissions" icon="plug">
How Phinite flags own-key usage at runtime.
</Card>
</CardGroup>
