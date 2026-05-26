---
title: "Jira"
description: "Issue tracking and project management via Jira API."
icon: "project-diagram"
---

## Overview

Phinite's Jira integration allows workspace assistants to create, search, update, and manage Jira issues, projects, and workflows programmatically.

This document explains what credentials are required, how to obtain them from Jira, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Create and update issues
- Search and filter issues
- Manage project workflows
- Add comments and attachments
- Transition issue statuses
- Access project information
- Generate reports

This integration is bidirectional and uses Jira's REST API.

## Required credentials

Phinite uses 3 credentials provided by Jira:

- Server URL (required)
- Username (required)
- API Token (required)

These credentials are generated through Jira account settings. Phinite does not modify or replace Jira's authentication model.

## Setup steps

### Step 1: Get Jira Server Details

For Jira Cloud:
1. Your Jira URL: https://yourcompany.atlassian.net
2. Note the server URL

For Jira Server/Data Center:
1. Your Jira server URL
2. Ensure API access is enabled

### Step 2: Create API Token

1. Go to Atlassian Account settings
2. Navigate to Security → Create and manage API tokens
3. Click "Create API token"
4. Give it a label (e.g., "Phinite Integration")
5. Copy the generated token

### Step 3: Get Username

1. Use your Atlassian account email address
2. This is the username for API authentication

### Step 4: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Jira
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Jira Production
   - Server URL: Your Jira server URL
   - Username: Your Atlassian email
   - API Token: Paste the API token
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Jira:

- Get Issue: Retrieve specific issue details
- Create Issue: Add new issues to projects
- Search Issues: Query issues with JQL
- Update Issue: Modify existing issues
- Add Comment: Comment on issues
- Transition Issue: Change issue status
- Get Projects: List available projects
- Create Project: Set up new projects
- Get Users: Access user information
- Assign Issue: Assign issues to users
- Add Attachment: Attach files to issues
- Get Issue Types: List issue types
- Get Workflows: Access project workflows
- Bulk Update: Modify multiple issues
- Get Dashboards: Access project dashboards
- Create Filter: Set up custom filters
- Get Sprints: Access agile sprints

## Documentation & resources

- Official Jira Documentation: `https://developer.atlassian.com/cloud/jira/platform/rest/v3/`
- Jira REST API Reference: `https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-issues/`
- Atlassian Developer Portal: `https://developer.atlassian.com/`

## Notes

- API tokens are user-specific and secure
- Jira has rate limits based on your plan
- Some operations require project permissions
- Monitor API usage to avoid limits
- Test with sandbox environments first
