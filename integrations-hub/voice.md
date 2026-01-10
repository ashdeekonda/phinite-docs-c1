---
title: "Voice"
description: "Voice calls and text-to-speech capabilities."
icon: "microphone"
---

## Overview

Phinite's Voice integration enables workspace assistants to make voice calls, generate text-to-speech audio, and handle voice communications through various voice service providers.

This document explains what credentials are required, how to configure voice services, and how to set up the integration inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Make outbound voice calls
- Generate text-to-speech audio
- Handle voice call workflows
- Record and transcribe calls
- Send voice messages
- Integrate with telephony systems

This integration uses various voice service APIs and telephony platforms.

## Required credentials

Phinite uses credentials specific to voice service providers:

- Twilio: Account SID, Auth Token, Phone Number
- Google Cloud Text-to-Speech: Service Account JSON
- AWS Polly: Access Key, Secret Key
- Azure Cognitive Services: API Key, Region
- Other providers: Service-specific credentials

These credentials are obtained from the respective voice service providers.

## Setup steps

### Step 1: Choose Voice Service Provider

Common providers supported:
- Twilio (telephony and voice)
- Google Cloud Text-to-Speech
- AWS Polly
- Azure Cognitive Services Speech
- Custom voice APIs

### Step 2: Get Provider Credentials

For Twilio:
1. Get Account SID and Auth Token from Twilio Console
2. Purchase or use existing phone number

For Google Cloud:
1. Enable Text-to-Speech API
2. Create service account and download JSON

For AWS Polly:
1. Create IAM user with Polly permissions
2. Get access key and secret

### Step 3: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Voice
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: Voice Service
   - Provider: Select voice provider
   - Credentials: Paste API keys/tokens
   - Phone Number: For telephony services
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Voice:

- Make Call: Initiate outbound voice calls
- Text to Speech: Generate audio from text
- Send Voice Message: Deliver voice recordings
- Record Call: Capture call audio
- Transcribe Audio: Convert speech to text
- Voice Synthesis: Create synthetic voices
- Call Transfer: Transfer active calls
- Get Call Status: Check call progress
- Play Audio: Stream audio during calls
- Gather Input: Collect caller responses
- Voice Biometrics: Speaker verification
- Language Detection: Identify spoken languages
- Sentiment Analysis: Analyze voice sentiment
- Noise Reduction: Clean up audio
- Voice Cloning: Create voice replicas

## Documentation & resources

- Twilio Voice Documentation: `https://www.twilio.com/docs/voice`
- Google Cloud Text-to-Speech: `https://cloud.google.com/text-to-speech`
- AWS Polly Documentation: `https://docs.aws.amazon.com/polly/`
- Azure Speech Services: `https://docs.microsoft.com/en-us/azure/cognitive-services/speech-service/`

## Notes

- Voice services incur per-minute charges
- API keys and phone numbers should be secured
- Monitor usage costs and call quality
- Different providers have varying voice quality
- Some features require premium service tiers
