---
title: "WhatsApp"
description: "WhatsApp messaging via Twilio or WhatsApp Business API."
icon: "whatsapp"
---

## Overview

Phinite's WhatsApp integration allows workspace assistants to send and receive WhatsApp messages through Twilio's WhatsApp API or WhatsApp Business API.

This document explains what credentials are required, how to obtain them from WhatsApp/Twilio, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Send text messages via WhatsApp
- Send media files and documents
- Receive WhatsApp messages
- Handle message templates
- Send location and contact information
- Manage conversation flows

This integration is bidirectional and uses WhatsApp's official APIs through approved providers.

## Required credentials

Phinite uses credentials from WhatsApp providers:

For Twilio WhatsApp:
- Account SID (required)
- Auth Token (required)
- WhatsApp Number (required)

For WhatsApp Business API:
- Access Token (required)
- Phone Number ID (required)
- Business Account ID (required)

These credentials are obtained from Twilio or Meta for WhatsApp Business API.

## Setup steps

### Option 1: Using Twilio WhatsApp

#### Step 1: Get Twilio Credentials

1. Sign up for Twilio account
2. Get Account SID and Auth Token from dashboard
3. Purchase a WhatsApp-enabled phone number

#### Step 2: Enable WhatsApp Sandbox

1. In Twilio Console, go to WhatsApp
2. Enable WhatsApp sandbox
3. Follow setup instructions
4. Connect your WhatsApp number

#### Step 3: Configure Webhooks (Optional)

1. Set message webhook URL
2. Configure status callback URL
3. Enable incoming message handling

### Option 2: Using WhatsApp Business API

#### Step 1: Create Meta Business Account

1. Go to Meta Business Manager
2. Create or access business account
3. Set up WhatsApp Business API access

#### Step 2: Get API Credentials

1. Generate permanent access token
2. Get Phone Number ID
3. Note Business Account ID

#### Step 3: Configure Webhooks

1. Set up webhook endpoints
2. Subscribe to message events
3. Verify webhook configuration

### Step 4: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select WhatsApp
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: WhatsApp Business
   - Provider: Select Twilio or WhatsApp Business API
   - Credentials: Enter appropriate API keys/tokens
   - Phone Number: Your WhatsApp number
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for WhatsApp:

- Send Text Message: Send WhatsApp text messages
- Send Media Message: Share images/audio/video
- Send Document: Send files and documents
- Send Location: Share GPS coordinates
- Send Contact: Share contact information
- Send Template Message: Use approved templates
- Receive Messages: Handle incoming messages
- Get Message Status: Check delivery status
- Create Template: Set up message templates
- Get Profile Info: Access contact information
- Mark as Read: Mark messages as read
- Send Interactive Message: Buttons and lists
- Send Sticker: Share WhatsApp stickers
- Get Media URL: Access media files
- Download Media: Retrieve media content
- Send Reply: Reply to specific messages
- Get Chat History: Access conversation history

## Documentation & resources

- WhatsApp Business API: `https://developers.facebook.com/docs/whatsapp/`
- Twilio WhatsApp: `https://www.twilio.com/docs/whatsapp`
- WhatsApp Business Policy: `https://www.whatsapp.com/business/policy`

## Notes

- WhatsApp Business API requires Meta approval
- Template messages must be pre-approved
- Rate limits apply to message sending
- Media files have size restrictions
- Monitor conversation quality scores
- Some features require premium access
