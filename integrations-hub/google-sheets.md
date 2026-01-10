---
title: "Google Sheets"
description: "Spreadsheet data access and manipulation."
icon: "table"
---

## Overview

Phinite's Google Sheets integration allows workspace assistants to read, write, and manipulate data in Google Sheets spreadsheets programmatically.

This document explains what credentials are required, how to obtain them from Google, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Read data from spreadsheet cells
- Write data to spreadsheets
- Create and manage sheets
- Format cells and ranges
- Create charts and formulas
- Share spreadsheets
- Access spreadsheet metadata

This integration is bidirectional and uses Google Sheets API.

## Required credentials

Phinite uses 1 credential provided by Google:

- Service Account JSON (required)

These credentials are generated through Google Cloud Console. Phinite does not modify or replace Google's authentication model.

## Setup steps

### Step 1: Create Google Cloud Project

1. Go to Google Cloud Console
2. Click Create Project or select existing project
3. Enter project name and click Create
4. Enable the Google Sheets API:
   - Go to APIs & Services > Library
   - Search for "Google Sheets API"
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

### Step 4: Share Spreadsheet Access

1. Open the Google Sheet you want to access
2. Click Share button
3. Enter the service account email (from JSON file)
4. Grant Editor or Viewer permissions
5. Click Send

### Step 5: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Google Sheets
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Google Sheets Production
   - Credentials: Upload the JSON file or paste JSON content
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Google Sheets:

- Read Range: Get data from cell ranges
- Write Range: Update spreadsheet cells
- Append Row: Add data to the end of sheets
- Create Sheet: Add new sheets to spreadsheets
- Delete Sheet: Remove sheets from spreadsheets
- Clear Range: Remove data from cell ranges
- Create Spreadsheet: Set up new spreadsheets
- Get Spreadsheet Info: Access spreadsheet metadata
- Update Sheet Properties: Modify sheet settings
- Add Chart: Create charts and graphs
- Format Range: Apply formatting to cells
- Create Filter: Add data filters
- Sort Range: Sort data in ranges
- Find and Replace: Search and modify content
- Get Sheet Values: Retrieve all sheet data
- Batch Update: Perform multiple operations

## Documentation & resources

- Official Sheets Documentation: `https://developers.google.com/sheets/api`
- Sheets API Reference: `https://developers.google.com/sheets/api/reference/rest`

## Notes

- Spreadsheets must be shared with service account
- API has rate limits (100 requests/second per user)
- Large spreadsheets may require pagination
- Some operations need specific permissions
- Monitor API usage to avoid limits
