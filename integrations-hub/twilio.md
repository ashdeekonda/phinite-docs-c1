---
title: "Twilio"
description: "Send SMS, make voice calls, and manage telephony through Twilio."
icon: "phone"
---

## Overview

Phinite’s Twilio integration enables assistants to send SMS/MMS, make voice calls, and manage phone communications using Twilio’s REST API.

<Frame>
  ![Twilio](/images/sampleimage.png)
</Frame>

## What this integration enables

- Send SMS and MMS
- Make automated voice calls
- Send WhatsApp messages via Twilio
- Check message delivery status
- Manage phone number inventory

## Required credentials

- Account SID (required)
- Auth Token (required)
- Phone Number (required for sending)

## Optional: webhooks

- Messaging webhook: `https://api.phinite.ai/webhooks/twilio` (POST)
- Voice webhook: `https://api.phinite.ai/webhooks/twilio/voice` (POST)

## Setup steps

<Steps>
  <Step title="Get credentials">
    Twilio Console → Dashboard → copy Account SID and Auth Token.
  </Step>
  <Step title="Buy number">
    Console → Phone Numbers → Buy a number with desired capabilities (Voice/SMS/MMS).
  </Step>
  <Step title="Configure in Phinite">
    Workspace → Integrations → Twilio → + Add Configuration. Enter name, Account SID, Auth Token, Phone Number. Select assistants. Save.
  </Step>
</Steps>

<Tip>
  Free trial accounts have limitations; production usage incurs per-message and per-minute costs.
</Tip>

## Predefined tools

- Send SMS
- Send MMS
- Make Call
- Send Voice Message
- Get Message Status
- List Messages
- Get Call Details
- Send WhatsApp
- Verify Phone
- Lookup Number

## Documentation & resources

- Docs: `https://www.twilio.com/docs`
- REST API Reference: `https://www.twilio.com/docs/usage/api`
- Console: `https://www.twilio.com/console`


