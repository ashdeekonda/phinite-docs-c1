---
title: "SlackTool"
description: "Slack messaging, threads, channel listing, and approval flows for Agent Graphs."
icon: "hashtag"
---

**SlackTool** posts messages, reads channel history, and supports approval-style subtools from Agent Graph nodes.

<Card title="Predefined tools hub" icon="plug" href="/devstudio/prebuilt-tools">
  Connection reuse and subtool enablement patterns.
</Card>

## Required configuration

| Field | Type | Notes |
| --- | --- | --- |
| `bot_token` | string | Bot token (typically `xoxb-…`) with required scopes |
| `app_token` | string | Optional — Socket Mode / advanced realtime (`xapp-…`) |

## Setup

1. Create a Slack app with scopes for enabled subtools (`chat:write`, `channels:read`, `channels:history`, etc.).
2. In Graph Studio → agent **Tools** tab, add **SlackTool** and create a connection with `bot_token`.
3. Invite the bot to private channels it must read or post to.
4. Enable subtools (for example `send_message`, `list_channels`) and **Save** the graph.

## Subtools

`send_for_approval`, `send_message_to_general`, `send_message`, `send_message_thread`, `list_channels`, `get_channel_history`

<Tip>
  Interactive approval subtools may require Slack event subscriptions and interactive components configured on your Slack app.
</Tip>

## Related

- [Slack channel deploy](/channels/slack)
- [Integrations Hub — Slack](/integrations-hub/slack)
