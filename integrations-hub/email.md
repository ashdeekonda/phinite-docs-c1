---
title: "Email (SMTP)"
description: "Send transactional and notification emails using SMTP providers."
icon: "envelope"
---

## Overview

Phinite’s Email integration sends transactional and notification emails using your SMTP provider (Gmail, Outlook/Office365, SendGrid, Mailgun, or custom SMTP).

<Frame>
  ![Email](/images/sampleimage.png)
</Frame>

## What this integration enables

- Send transactional and notification emails
- HTML emails and templates
- Attachments, CC/BCC, multiple recipients
- Scheduling and priority
- Replies and forwarding

## Required credentials

- SMTP Server Host (required)
- SMTP Port (required)
- Email Address (required)
- Password or App Password (required)

## Setup steps

<Steps>
  <Step title="Get SMTP credentials">
    Obtain SMTP host, port, username (email), and password/app password from your provider.
  </Step>
  <Step title="Configure in Phinite">
    Workspace → Integrations → Email → + Add Configuration. Enter host, port (usually 587), email address, password, and enable TLS if required. Test connection and save.
  </Step>
</Steps>

<Note>
  Use app-specific passwords (e.g., Gmail/Outlook) and enable TLS/SSL for secure delivery.
</Note>

## Predefined tools

- Send Email
- Send HTML Email
- Send with Attachments
- Send to Multiple Recipients
- Send with CC/BCC
- Send Template Email
- Schedule Email
- Send Reply
- Forward Email
- Send with Priority

## Documentation & resources

- Gmail SMTP: `https://support.google.com/mail/answer/7126229`
- Outlook SMTP: `https://support.microsoft.com/en-us/office/pop-imap-and-smtp-settings-8361e398-8af4-4e97-b147-6c6c4ac95353`
- SendGrid: `https://docs.sendgrid.com/`
- Mailgun: `https://documentation.mailgun.com/`


