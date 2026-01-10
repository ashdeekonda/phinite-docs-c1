---
title: "API"
description: "Generic HTTP client for arbitrary API integrations."
icon: "code"
---

## Overview

Phinite's API integration provides a generic HTTP client that allows workspace assistants to connect to any REST API or web service programmatically.

This document explains how to configure API connections and set up the integration inside Phinite for custom API access.

## What this integration enables

Once configured, Phinite assistants can:

- Make HTTP requests to any API
- Handle authentication methods
- Process JSON/XML responses
- Manage rate limiting
- Handle webhooks and callbacks
- Integrate with custom services

This integration is bidirectional and supports standard HTTP methods.

## Required credentials

Phinite uses flexible credential configuration:

- Base URL (required)
- Authentication method (optional)
- API Key/Header/Token (optional)
- Username/Password (optional)
- Custom headers (optional)

These credentials depend on the target API requirements.

## Setup steps

### Step 1: Identify Target API

1. Determine the API you want to connect to
2. Review the API documentation
3. Note required authentication and endpoints
4. Understand rate limits and requirements

### Step 2: Configure Authentication

Common authentication methods:
- API Key in header
- Bearer token
- Basic authentication
- OAuth 2.0
- Custom authentication

### Step 3: Set Connection Parameters

1. Base URL of the API
2. Authentication credentials
3. Default headers
4. Timeout settings
5. Retry configuration

### Step 4: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select API
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: API Service Name
   - Base URL: The API base URL
   - Authentication: Choose auth method
   - Credentials: Enter API keys/tokens
   - Headers: Add custom headers
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for API:

- Make GET Request: Retrieve data from APIs
- Make POST Request: Send data to APIs
- Make PUT Request: Update API resources
- Make PATCH Request: Partial resource updates
- Make DELETE Request: Remove API resources
- Upload File: Send files via API
- Download File: Retrieve files from API
- Handle Webhooks: Process incoming webhooks
- OAuth Flow: Handle OAuth authentication
- API Pagination: Handle paginated responses
- Rate Limiting: Respect API rate limits
- Error Handling: Manage API errors
- Response Parsing: Process different data formats
- Request Signing: Sign requests for security
- API Testing: Validate endpoints
- Monitoring: Track API performance

## Documentation & resources

- REST API Best Practices: `https://restfulapi.net/`
- HTTP Status Codes: `https://httpstatuses.com/`
- API Authentication Methods: `https://tools.ietf.org/html/rfc6749`

## Notes

- Always respect API terms of service
- Implement proper error handling
- Monitor rate limits and usage
- Keep API keys and credentials secure
- Test integrations thoroughly before production use
