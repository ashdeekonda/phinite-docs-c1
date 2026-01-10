---
title: "Chat (AI)"
description: "AI chat actions and conversational AI integration."
icon: "comments"
---

## Overview

Phinite's Chat AI integration allows workspace assistants to interact with various AI chat models and conversational AI services for enhanced communication capabilities.

This document explains what credentials are required, how to configure AI service connections, and how to set up the integration inside Phinite.

## What this integration enables

Once configured, Phinite assistants can:

- Generate AI-powered responses
- Access multiple AI chat models
- Create conversational workflows
- Integrate with chat-based AI services
- Handle natural language processing
- Generate creative content

This integration is outbound and uses various AI service APIs.

## Required credentials

Phinite uses credentials specific to each AI service:

- OpenAI: API Key
- Anthropic: API Key
- Google AI: API Key
- Other services: Service-specific credentials

These credentials are obtained from the respective AI service providers.

## Setup steps

### Step 1: Choose AI Service Provider

Common providers supported:
- OpenAI (GPT models)
- Anthropic (Claude models)
- Google AI (Gemini models)
- Custom AI endpoints

### Step 2: Get API Credentials

For OpenAI:
1. Go to OpenAI Platform
2. Create API key
3. Copy the key

For Anthropic:
1. Go to Anthropic Console
2. Generate API key
3. Copy the key

For Google AI:
1. Go to Google AI Studio
2. Get API key
3. Copy the key

### Step 3: Configure in Phinite

1. Log into your Phinite workspace at www.phinite.ai
2. Navigate to Integrations
3. Select Chat AI
4. Click + Add Configuration
5. Enter the following:
   - Name of the connection: AI Chat Service
   - Provider: Select AI provider
   - API Key: Paste your API key
   - Model: Choose specific model (optional)
6. Select the workspace assistants that should use this connection
7. Click Save Configuration

## Predefined tools

Phinite provides these predefined actions for Chat AI:

- Generate Response: Create AI text responses
- Chat Completion: Complete conversational turns
- Summarize Text: Generate text summaries
- Translate Text: Language translation
- Generate Ideas: Brainstorming and ideation
- Answer Questions: Q&A functionality
- Create Content: Generate articles/stories
- Code Generation: Write and explain code
- Sentiment Analysis: Analyze text sentiment
- Language Detection: Identify languages
- Text Classification: Categorize content
- Named Entity Recognition: Extract entities
- Paraphrase Text: Rewrite content
- Grammar Check: Correct writing
- Tone Analysis: Analyze communication style

## Documentation & resources

- OpenAI Documentation: `https://platform.openai.com/docs`
- Anthropic Documentation: `https://docs.anthropic.com/`
- Google AI Documentation: `https://ai.google.dev/docs`

## Notes

- API keys should be kept secure
- AI services have usage costs and rate limits
- Monitor token usage and costs
- Different models have varying capabilities
- Some services require specific API versions
