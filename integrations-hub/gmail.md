---
title: "Gmail"
description: "Read/search/draft/send/reply Gmail-like accounts."
icon: "envelope"
---

## Overview

Phinite's Gmail integration allows workspace assistants to read, search, draft, send, and reply to emails in Gmail accounts programmatically.

This document explains what credentials are required, how to obtain them from Google, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Read emails from inbox and folders
- Search emails by various criteria
- Send new emails and replies
- Create and manage drafts
- Access email attachments
- Organize emails with labels

This integration is bidirectional and uses Gmail's official API.

## Required credentials

Phinite uses 2 credentials provided by Google:

- Email Address (required)
- App Password (required)

These credentials are generated through Google Account settings. Phinite does not modify or replace Google's authentication model.

## Setup steps

### Step 1: Enable 2-Factor Authentication

1. Go to Google Account settings
2. Navigate to Security
3. Enable 2-Step Verification
4. Complete the setup process

### Step 2: Generate App Password

1. In Google Account Security settings
2. Go to "App passwords"
3. Select "Mail" and your device type
4. Click "Generate"
5. Copy the 16-character password

### Step 3: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Gmail
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Gmail Account
   - Email Address: Your Gmail address
   - App Password: Paste the app password
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Gmail:

- Get Latest Emails: Retrieve recent messages
- Get Emails from User: Find emails from specific senders
- Get Unread Emails: Access unread messages
- Get Starred Emails: Retrieve starred messages
- Get Emails by Context: Search by keywords/subject
- Get Emails by Date: Filter by date ranges
- Get Emails by Thread: Access conversation threads
- Search Emails: Advanced search functionality
- Create Draft Email: Save email drafts
- Send Email: Send new emails
- Send Email Reply: Reply to existing emails

## Documentation & resources

- Official Gmail Documentation: `https://developers.google.com/gmail/api`
- Gmail API Reference: `https://developers.google.com/gmail/api/reference/rest`
- Google App Passwords: `https://support.google.com/accounts/answer/185833`

## Notes

- App passwords are required for 2FA-enabled accounts
- Gmail API has daily sending limits (500 emails/day for free accounts)
- Some operations may require additional Gmail API scopes
- Monitor API usage to avoid hitting limits
- Attachments have size restrictions
