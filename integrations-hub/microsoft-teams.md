---
title: "Microsoft Teams"
description: "Team collaboration and messaging via Microsoft Teams."
icon: "people-group"
---

## Overview

Phinite's Microsoft Teams integration allows workspace assistants to interact with Microsoft Teams for messaging, collaboration, and workflow automation.

This document explains what credentials are required, how to obtain them from Microsoft Azure, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Send messages to Teams channels
- Create and manage teams
- Handle approvals and workflows
- Access team files and content
- Send proactive notifications
- Integrate with Microsoft Graph

This integration is bidirectional and uses Microsoft Graph API.

## Required credentials

Phinite uses 3 credentials provided by Microsoft Azure:

- App ID (required)
- App Secret (required)
- Tenant ID (required)

These credentials are generated through Azure App Registrations. Phinite does not modify or replace Microsoft's authentication model.

## Setup steps

### Step 1: Create Azure App Registration

1. Go to Azure Portal
2. Navigate to Azure Active Directory > App registrations
3. Click "New registration"
4. Enter app name (e.g., "Phinite Teams Bot")
5. Choose account type (single tenant/org)
6. Click Register

### Step 2: Configure API Permissions

1. Go to API permissions in your app
2. Add Microsoft Graph permissions:
   - ChannelMessage.Send
   - Chat.ReadWrite
   - Team.ReadBasic.All
   - Files.ReadWrite.All
   - User.Read.All
3. Grant admin consent for permissions

### Step 3: Create Client Secret

1. Go to Certificates & secrets
2. Click "New client secret"
3. Add description and expiration
4. Copy the secret value immediately

### Step 4: Get App Details

1. Copy Application (client) ID
2. Copy Directory (tenant) ID from overview
3. Keep the client secret secure

### Step 5: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Microsoft Teams
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Teams Production
   - App ID: Paste the Application ID
   - App Secret: Paste the client secret
   - Tenant ID: Paste the Directory ID
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Microsoft Teams:

- Send Channel Message: Post to team channels
- Send Chat Message: Direct messages to users
- Create Team: Set up new teams
- Add Team Member: Invite users to teams
- Create Channel: Add channels to teams
- Send Approval Request: Create approval workflows
- Get Team Info: Access team details
- List Channels: View team channels
- Upload File: Share files in teams
- Get Messages: Retrieve channel messages
- Reply to Message: Respond in threads
- Create Meeting: Schedule Teams meetings
- Get User Presence: Check user status
- Send Adaptive Card: Rich message formatting
- Handle Approvals: Process approval responses
- Get Files: Access team file libraries
- Create Tab: Add custom tabs to channels

## Documentation & resources

- Official Teams Documentation: `https://docs.microsoft.com/en-us/microsoftteams/`
- Microsoft Graph API: `https://docs.microsoft.com/en-us/graph/api/overview`
- Azure App Registration: `https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app`

## Notes

- Graph API permissions require admin consent
- Teams bots have specific rate limits
- Some features need premium licenses
- Monitor API usage and permissions
- Test integrations in development tenants first
