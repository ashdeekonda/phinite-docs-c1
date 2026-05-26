---
title: "Google Drive"
description: "File storage and management via Google Drive API."
icon: "folder-open"
---

## Overview

Phinite's Google Drive integration allows workspace assistants to upload, download, organize, and manage files in Google Drive.

This document explains what credentials are required, how to obtain them from Google, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Upload and download files
- Create and organize folders
- Search for files and folders
- Share files with permissions
- Access file metadata
- Manage file versions
- Export Google Workspace files

This integration is bidirectional and uses Google Drive API.

## Required credentials

Phinite uses 1 credential provided by Google:

- Service Account JSON (required)

These credentials are generated through Google Cloud Console. Phinite does not modify or replace Google's authentication model.

## Setup steps

### Step 1: Create Google Cloud Project

1. Go to Google Cloud Console
2. Click Create Project or select existing project
3. Enter project name and click Create
4. Enable the Google Drive API:
   - Go to APIs & Services > Library
   - Search for "Google Drive API"
   - Click Enable

### Step 2: Create Service Account

1. In Google Cloud Console, go to IAM & Admin > Service Accounts
2. Click Create Service Account
3. Enter service account name and description
4. Click Create and Continue
5. Skip role assignment (click Continue)
6. Click Done

### Step 3: Generate Service Account Key

1. Click on the created service account
2. Go to Keys tab
3. Click Add Key > Create new key
4. Select JSON format
5. Click Create
6. Download the JSON file and keep it secure

### Step 4: Configure Domain-wide Delegation (Optional)

1. For organization-wide access, enable domain-wide delegation
2. Add necessary scopes in Google Workspace admin console
3. This allows access to all users' drives in the organization

### Step 5: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Google Drive
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Google Drive Production
   - Credentials: Upload the JSON file or paste JSON content
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Google Drive:

- Upload File: Add files to Drive
- Download File: Retrieve files from Drive
- Create Folder: Set up new folders
- List Files: Browse folder contents
- Search Files: Find files by name/content
- Get File Info: Access file metadata
- Update File: Modify file properties
- Delete File: Remove files from Drive
- Copy File: Duplicate files
- Move File: Relocate files between folders
- Share File: Grant access permissions
- Create Permission: Set sharing permissions
- Export File: Convert Google files to other formats
- Create Shortcut: Make file shortcuts
- Get Comments: Access file comments
- Add Comment: Comment on files
- Watch Changes: Monitor file modifications
- Empty Trash: Clean up deleted files

## Documentation & resources

- Official Drive Documentation: `https://developers.google.com/drive/api`
- Drive API Reference: `https://developers.google.com/drive/api/reference/rest`

## Notes

- Service accounts have limited sharing capabilities
- Domain-wide delegation required for org-wide access
- API has rate limits and quota restrictions
- Large files may require resumable uploads
- Monitor storage quotas and API usage
