---
title: "Telegram"
description: "Messaging via Telegram Bot API."
icon: "paper-plane"
---

## Overview

Phinite's Telegram integration allows workspace assistants to send and receive messages through Telegram bots, enabling automated communication and notifications.

This document explains what credentials are required, how to obtain them from Telegram, and how to configure them inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Send messages to Telegram chats
- Receive messages from users
- Send photos, documents, and media
- Create inline keyboards and buttons
- Handle group chats and channels
- Set up automated responses

This integration is bidirectional and uses Telegram's official Bot API.

## Required credentials

Phinite uses 1 credential provided by Telegram:

- Bot Token (required)

These credentials are generated through Telegram's BotFather. Phinite does not modify or replace Telegram's authentication model.

## Setup steps

### Step 1: Create Telegram Bot

1. Open Telegram app and search for @BotFather
2. Start a chat with BotFather
3. Send command: /newbot
4. Follow prompts to:
   - Choose a name for your bot
   - Choose a username (must end with 'bot')
5. BotFather will provide your bot token

### Step 2: Get Bot Token

1. Copy the token provided by BotFather
2. Keep this token secure and never share it
3. The token format is: `123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11`

### Step 3: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Telegram
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Telegram Bot
   - Bot Token: Paste your bot token
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Telegram:

- Send Message: Send text messages to chats
- Send Photo: Share images with captions
- Send Document: Send files and documents
- Send Location: Share GPS coordinates
- Send Contact: Share contact information
- Create Poll: Send interactive polls
- Send Sticker: Send Telegram stickers
- Forward Message: Forward messages between chats
- Get Chat Info: Retrieve chat details
- Get Updates: Poll for new messages
- Send Inline Keyboard: Create interactive buttons
- Edit Message: Modify sent messages
- Delete Message: Remove messages
- Pin Message: Pin important messages
- Get File: Download files from Telegram
- Send Voice: Send voice messages
- Send Video: Share video content

## Documentation & resources

- Official Telegram Documentation: `https://core.telegram.org/bots`
- Telegram Bot API Reference: `https://core.telegram.org/bots/api`
- BotFather: `https://t.me/botfather`

## Notes

- Telegram bots cannot initiate conversations with users
- Users must start the conversation first
- Bot tokens should be kept secure
- Telegram has rate limits on API calls
- Bots can be added to groups and channels
