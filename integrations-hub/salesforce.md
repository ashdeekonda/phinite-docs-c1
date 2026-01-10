---
title: "Salesforce"
description: "CRM and sales data via Salesforce APIs."
icon: "cloud"
---

## Overview

Phinite's Salesforce integration allows workspace assistants to access and manage Salesforce CRM data, including leads, opportunities, accounts, contacts, and custom objects.

This document explains what credentials are required, how to obtain them from Salesforce, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Read and update Salesforce records
- Create new leads, accounts, and opportunities
- Query Salesforce data with SOQL
- Access custom objects and fields
- Sync data between systems

This integration is bidirectional and uses Salesforce's official REST API.

## Required credentials

Phinite uses 3 credentials provided by Salesforce:

- Consumer Key (required)
- Consumer Secret (required)
- Username (required)

These credentials are generated through Salesforce Connected Apps. Phinite does not modify or replace Salesforce's authentication model.

## Setup steps

### Step 1: Create Connected App in Salesforce

1. Log into your Salesforce org
2. Go to Setup (gear icon)
3. In Quick Find, search "App Manager"
4. Click New Connected App
5. Fill in basic information:
   Connected App Name: "Phinite Integration"
   API Name: "Phinite_Integration"
   Contact Email: your email
6. Enable OAuth settings and specify callback URL(s)
7. Add necessary OAuth scopes (api, refresh_token, offline_access)
8. Save the connected app and wait for it to provision
9. Copy the Consumer Key and Consumer Secret

### Step 2: Get Username and Password

1. Use your Salesforce username (email address)
2. If using password authentication, get your Salesforce password
3. For enhanced security, consider using OAuth refresh tokens

### Step 3: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Salesforce
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Salesforce Production
   - Consumer Key: Paste the Consumer Key from your Connected App
   - Consumer Secret: Paste the Consumer Secret from your Connected App
   - Username: Your Salesforce username (email)
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Salesforce:

- Query Records: Execute SOQL queries to retrieve data
- Create Record: Add new records to Salesforce objects
- Update Record: Modify existing record data
- Delete Record: Remove records from Salesforce
- Describe Object: Get metadata about Salesforce objects
- Get Record: Retrieve specific record details
- Search Records: Perform SOSL searches
- Create Lead: Generate new sales leads
- Update Opportunity: Modify opportunity details
- Get Account Info: Access account information
- List Contacts: Retrieve contact lists
- Bulk Operations: Handle multiple records at once

## Documentation & resources

- Official Salesforce Documentation: `https://developer.salesforce.com/docs/`
- Salesforce REST API Reference: `https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/`
- Salesforce SOQL Reference: `https://developer.salesforce.com/docs/atlas.en-us.soql_sosl.meta/soql_sosl/`

## Notes

- Salesforce has API limits based on your edition
- Use OAuth 2.0 for enhanced security
- Respect Salesforce governor limits on API calls
- Connected Apps require admin approval in some orgs
- Monitor API usage to avoid hitting limits
