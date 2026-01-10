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

