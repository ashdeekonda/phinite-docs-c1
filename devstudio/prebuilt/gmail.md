---
title: "GmailTool"
description: "Read/search/draft/send/reply Gmail-like accounts."
icon: "envelope"
---

## GmailTool

Required configuration:
- `email` (string)
- `app_password` (string)

Typical validations:
- List labels; fetch one message metadata

### Subtools
- `get_latest_emails`, `get_emails_from_user`, `get_unread_emails`, `get_starred_emails`,
  `get_emails_by_context`, `get_emails_by_date`, `get_emails_by_thread`,
  `search_emails`, `create_draft_email`, `send_email`, `send_email_reply`

### Troubleshooting
- Auth errors, quota limits, large attachments
---
title: "Gmail Integration"
description: "Send and read emails via Gmail."
icon: envelope
---

## Parameters

<ParamField body="to" type="string" required>Recipient email address</ParamField>
<ParamField body="subject" type="string" required>Email subject</ParamField>
<ParamField body="body" type="string" required>Email body</ParamField>

## Example

<RequestExample>
```json Tool Input
{
  "to": "user@example.com",
  "subject": "Hello",
  "body": "Hi there!"
}
```
</RequestExample>

<ResponseExample>
```json Success
{ "status": "sent", "id": "msg_123" }
```
</ResponseExample>
