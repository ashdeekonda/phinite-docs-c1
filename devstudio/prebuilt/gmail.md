---
title: "GmailTool"
description: "Read, search, draft, send, and reply to Gmail-like accounts from Agent Graph nodes."
icon: "envelope"
---

**GmailTool** automates inbox operations for Agent Graphs that handle email triage, notifications, or outbound messages.

<Card title="Predefined tools hub" icon="plug" href="/devstudio/prebuilt-tools">
  How connections, subtools, and Graph Studio linking work across integrations.
</Card>

## Required configuration

| Field | Type | Notes |
| --- | --- | --- |
| `email` | string | Mailbox address for this connection |
| `app_password` | string | App password or IMAP/SMTP credential (store via secure connection UI) |

## Setup

1. In Graph Studio, open an agent node **Tools** tab → **Add tool** → **GmailTool**.
2. **Add a new connection** with `email` and `app_password`.
3. Validate by listing labels or fetching one message metadata (no body).
4. Enable subtools your graph needs (read-only vs send-capable).
5. **Save** the graph and test with a small `get_latest_emails` call.

## Subtools

`get_latest_emails`, `get_emails_from_user`, `get_unread_emails`, `get_starred_emails`, `get_emails_by_context`, `get_emails_by_date`, `get_emails_by_thread`, `search_emails`, `create_draft_email`, `send_email`, `send_email_reply`

## Example input

<RequestExample>

```json Tool Input
{
  "count": 5,
  "include_body": false
}
```

</RequestExample>

<ResponseExample>

```json Success
{ "messages": [{ "id": "msg_123", "subject": "Hello" }] }
```

</ResponseExample>

## Troubleshooting

- **Auth errors** — verify `email` matches the app password account and IMAP/API access is enabled.
- **Quota / rate limits** — split high-volume graphs across connections.
- **Large attachments** — prefer links from object storage instead of inline sends.

<Note>
  For OAuth-based Gmail via workspace [Integrations](/configure/integrations), follow your org's connector setup; this tool documents app-password style connections.
</Note>
