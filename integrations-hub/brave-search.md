---
title: "Brave Search"
description: "Privacy-first web search using Brave's independent search engine."
icon: "magnifying-glass"
---

## Overview

Phinite's Brave Search integration allows workspace assistants to perform web searches using Brave's independent search engine and retrieve search results programmatically.

This document explains what credentials are required, how to obtain them from Brave Search API, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Perform web searches with privacy-focused results
- Retrieve search results in structured format
- Access news and image search results
- Get real-time web information
- Conduct research queries

This integration is outbound-only and uses Brave Search's official API.

## Required credentials

Phinite uses 1 credential provided by Brave Search:

- API Key (required)

These credentials are generated through Brave Search API platform. Phinite does not modify or replace Brave's authentication model.

## Setup steps

### Step 1: Create Brave Search API Account

1. Go to Brave Search API website
2. Click Sign Up or Get Started
3. Complete account registration
4. Verify your email address
5. Log into your Brave Search dashboard

### Step 2: Generate API Key

1. In Brave Search dashboard, navigate to API Keys
2. Click Create New API Key
3. Enter a descriptive name (e.g., "Phinite Integration")
4. Select appropriate permissions
5. Click Generate Key
6. Copy the API key immediately (it won't be shown again)

### Step 3: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Brave Search
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Brave Search Production
   - API Key: Paste the API key you copied
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Brave Search:

- Web Search: Perform general web searches
- News Search: Get recent news articles
- Image Search: Find images by keywords
- Local Search: Search for local businesses
- Video Search: Find videos on topics
- Spell Check: Check spelling and grammar
- Instant Answer: Get quick facts and answers
- Suggestions: Get search suggestions
- Search History: Access previous searches
- Custom Search: Advanced search parameters

## Documentation & resources

- Official Brave Search Documentation: `https://api.search.brave.com/`
- Brave Search API Reference: `https://api.search.brave.com/app/documentation`

## Notes

- Brave Search API has rate limits based on your plan
- Results are privacy-focused with no tracking
- API supports multiple search types and filters
- Monitor usage to stay within plan limits
