---
title: "Slack"
description: "Team messaging and collaboration via Slack API."
icon: "hashtag"
---

## Overview

Phinite's Slack integration allows workspace assistants to send messages, manage channels, handle threads, and automate workflows in Slack workspaces.

This document explains what credentials are required, how to obtain them from Slack, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Send messages to channels and users
- Create and manage channels
- Handle message threads
- Upload and share files
- Set up automated responses
- Access channel history
- Send approval requests

This integration is bidirectional and uses Slack's API.

## Required credentials

Phinite uses 2 credentials provided by Slack:

- Bot User OAuth Token (required)
- Signing Secret (required)

These credentials are generated through Slack App settings. Phinite does not modify or replace Slack's authentication model.

## Setup steps

### Step 1: Create Slack App

1. Go to Slack API website
2. Click "Create New App"
3. Choose "From scratch"
4. Enter app name and select workspace
5. Click "Create App"

### Step 2: Configure Bot Token Scopes

1. In your app settings, go to "OAuth & Permissions"
2. Add Bot Token Scopes:
   - channels:read
   - channels:history
   - chat:write
   - files:read
   - files:write
   - im:read
   - im:history
   - users:read
   - groups:read
3. Install the app to your workspace
4. Copy the Bot User OAuth Token

### Step 3: Get Signing Secret

1. Go to "Basic Information" in app settings
2. Find "App Credentials" section
3. Copy the Signing Secret

### Step 4: Configure Event Subscriptions (Optional)

1. Go to "Event Subscriptions"
2. Enable events for real-time messaging
3. Add bot events (message.channels, app_mention)
4. Set request URL if needed

### Step 5: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Slack
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Slack Workspace
   - Bot Token: Paste the OAuth token
   - Signing Secret: Paste the signing secret
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Slack:

- Send Message to General: Post to main channel
- Send Message: Send to specific channels/users
- Send Message Thread: Reply in threads
- List Channels: Get workspace channels
- Get Channel History: Access message history
- Create Channel: Set up new channels
- Upload File: Share files in Slack
- Send for Approval: Create approval workflows
- Get User Info: Access user details
- Search Messages: Find messages by content
- Pin Message: Pin important messages
- Add Reaction: React to messages
- Invite User: Invite users to channels
- Archive Channel: Archive channels
- Get Team Info: Access workspace details
- Send Ephemeral Message: Private user messages
- Update Message: Edit sent messages
- Delete Message: Remove messages

## Documentation & resources

- Official Slack Documentation: `https://api.slack.com/`
- Slack API Reference: `https://api.slack.com/methods`
- Slack App Management: `https://api.slack.com/apps`

## Notes

- Bot tokens start with xoxb-
- Apps need to be installed to workspaces
- Some scopes require admin approval
- Monitor rate limits (50 requests/minute for most methods)
- Test integrations in sandbox workspaces
