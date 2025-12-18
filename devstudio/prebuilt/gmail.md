---
title: "Gmail Integration"
description: "Send and read emails via Gmail."
icon: "envelope"
---

## Parameters

<ParamField body="to" type="string" required>
  Recipient email address
</ParamField>

 <ParamField body="subject" type="string" required>
  Email subject
</ParamField>

 <ParamField body="body" type="string" required>
  Email body
</ParamField>


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