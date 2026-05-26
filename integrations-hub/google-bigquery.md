---
title: "Google BigQuery"
description: "Analytics warehouse for large-scale data analysis."
icon: "database"
---

## Overview

Phinite's Google BigQuery integration allows workspace assistants to query, analyze, and manage large datasets in Google BigQuery data warehouse.

This document explains what credentials are required, how to obtain them from Google Cloud, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Execute SQL queries on BigQuery datasets
- Create and manage tables and views
- Load data into BigQuery
- Export query results
- Monitor query performance
- Access public datasets

This integration is bidirectional and uses BigQuery's official API.

## Required credentials

Phinite uses 1 credential provided by Google Cloud:

- Service Account JSON (required)

These credentials are generated through Google Cloud Console. Phinite does not modify or replace Google's authentication model.

## Setup steps

### Step 1: Create Google Cloud Project

1. Go to Google Cloud Console
2. Click Create Project or select existing project
3. Enter project name and click Create
4. Enable the BigQuery API:
   - Go to APIs & Services > Library
   - Search for "BigQuery API"
   - Click Enable

### Step 2: Create Service Account

1. In Google Cloud Console, go to IAM & Admin > Service Accounts
2. Click Create Service Account
3. Enter service account name and description
4. Click Create and Continue
5. Grant BigQuery roles:
   - BigQuery User
   - BigQuery Data Viewer/Editor (as needed)
6. Click Continue, then Done

### Step 3: Generate Service Account Key

1. Click on the created service account
2. Go to Keys tab
3. Click Add Key > Create new key
4. Select JSON format
5. Click Create
6. Download the JSON file and keep it secure

### Step 4: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Google BigQuery
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: BigQuery Production
   - Project ID: Your Google Cloud project ID
   - Credentials: Upload the JSON file or paste JSON content
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Google BigQuery:

- Execute Query: Run SQL queries and get results
- Create Table: Set up new tables in datasets
- Insert Data: Load data into existing tables
- Update Data: Modify table records
- Delete Data: Remove data from tables
- Create Dataset: Set up new datasets
- List Datasets: View available datasets
- List Tables: Access tables in datasets
- Get Table Schema: Retrieve table structure
- Export Data: Export query results
- Create View: Set up database views
- Run Job: Execute long-running queries
- Check Job Status: Monitor query progress
- Get Query Results: Retrieve completed query results
- Cancel Job: Stop running queries
- Get Dataset Info: Access dataset metadata

## Documentation & resources

- Official BigQuery Documentation: `https://cloud.google.com/bigquery/docs`
- BigQuery API Reference: `https://cloud.google.com/bigquery/docs/reference/rest`
- BigQuery SQL Reference: `https://cloud.google.com/bigquery/docs/reference/standard-sql`

## Notes

- BigQuery charges for storage and query processing
- Service accounts need appropriate BigQuery permissions
- Large queries may take time to execute
- Monitor costs for data storage and processing
- Public datasets are accessible without credentials
