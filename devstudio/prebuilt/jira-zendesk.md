---
title: "Jira & Zendesk Integrations"
description: "Create and update tickets in Jira and Zendesk."
icon: ticket
---

## Parameters

<ParamField body="title" type="string" required>Ticket title</ParamField>
<ParamField body="description" type="string" required>Ticket description</ParamField>
<ParamField body="priority" type="string">Priority level</ParamField>

## Example

<RequestExample>
```json Tool Input
{
  "title": "Login error",
  "description": "Users cannot log in after password reset",
  "priority": "High"
}
```
</RequestExample>

<ResponseExample>
```json Success
{ "id": "JIRA-123", "status": "created" }
```
</ResponseExample>
