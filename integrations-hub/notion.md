---
title: "Notion"
description: "Docs and databases integration with Notion API."
icon: "note-sticky"
---

## Overview

Phinite's Notion integration allows workspace assistants to read, create, and update documents, databases, and pages in Notion workspaces.

This document explains what credentials are required, how to obtain them from Notion, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Read and write Notion pages
- Create and update databases
- Search for content across workspaces
- Add comments to pages
- Manage page properties
- Create templates and automations

This integration is bidirectional and uses Notion's official API.

## Required credentials

Phinite uses 1 credential provided by Notion:

- Internal Integration Token (required)

These credentials are generated through Notion's developer portal. Phinite does not modify or replace Notion's authentication model.

## Setup steps

### Step 1: Create Notion Integration

1. Go to Notion Developers website
2. Sign in with your Notion account
3. Click "New integration"
4. Fill in integration details:
   - Name: "Phinite Integration"
   - Associated workspace: Select your workspace
   - Type: Internal
5. Click "Submit"

### Step 2: Get Integration Token

1. After creation, you'll see the "Internal Integration Token"
2. Click "Show" to reveal the token
3. Copy the token (format: secret_...)
4. Keep this token secure

### Step 3: Share Pages with Integration

1. Open the pages/databases you want to access
2. Click "Share" in the top right
3. Search for your integration name
4. Select it and grant appropriate permissions
5. Repeat for all pages you want to access

### Step 4: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Notion
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Notion Workspace
   - Integration Token: Paste your internal integration token
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Notion:

- Create Page: Add new pages to workspaces
- Update Page: Modify existing page content
- Delete Page: Remove pages from workspaces
- Get Page: Retrieve page content and metadata
- Search Pages: Find pages by title or content
- Create Database: Set up new databases
- Query Database: Retrieve database entries
- Update Database Item: Modify database records
- Add Comment: Comment on pages
- Get Block Children: Access page block content
- Append Block Children: Add content to pages
- Update Block: Modify individual blocks
- Delete Block: Remove blocks from pages
- Get User: Retrieve user information
- List Users: Get workspace users
- Create Template: Set up reusable templates

## Documentation & resources

- Official Notion Documentation: `https://developers.notion.com/`
- Notion API Reference: `https://developers.notion.com/reference`
- Notion Developer Portal: `https://developers.notion.com/`

## Notes

- Integration tokens are workspace-specific
- Pages must be shared with the integration
- Notion has rate limits on API calls
- Some content types may require specific permissions
- Integration capabilities depend on workspace plan
