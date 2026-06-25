---
title: "Core concepts"
description: "What assistants, agent graphs, tools, triggers, channels, builds, and the Agent Registry mean in Phinite — with links to where you work in the product."
---

Phinite assistants are built from a small set of concepts. Each section below explains **what it is**, **when you need it**, and **where to go in the docs** for procedures.

## Assistants

An **assistant** is a deployable product surface (conversational chat/voice, email automation, or autonomous workflows) backed by **agent graphs**, **tools**, and optional **channels**.

- [Assistant types](/assistants/types) — Conversational, Email, Autonomous
- [Conversational assistants](/assistants/conversational)
- [Email assistants](/assistants/email)
- [Autonomous assistants](/assistants/autonomous)

## Agent graphs

**Agent graphs** are the orchestration layer: nodes, edges, prompts, tools, and routing on the Graph Studio canvas. Every assistant runs one or more published agent graphs.

- [Graph Studio overview](/graph-studio/overview)
- [Publishing agent graphs](/graph-studio/publishing)
- After publishing, [expose as an A2A agent](/agent-registry/publish#expose-wizard) to register an Agent Card and hosted URL

## Tools

**Tools** are callable actions — integrations, APIs, or custom Python — that agent nodes invoke. Author tools in DevStudio; connect credentials via Integrations Hub.

- [DevStudio overview](/devstudio/overview)
- [Integrations Hub overview](/integrations-hub/overview)

## Intents and triggers

**Intents** classify user language; **triggers** start agent graphs from APIs, schedules, webhooks, or events.

- [Triggers & Intents overview](/triggers-intents/overview)
- [Intents guide](/triggers-intents/intents-guide)
- [Triggers guide](/triggers-intents/triggers-guide)
- [Email intents](/concepts/overview#intents-and-triggers-email)

## Channels

**Channels** are where end users talk to assistants — webchat, WhatsApp, Slack, Teams, Twilio voice, email.

- [Connect overview](/connect/overview)
- [Channels setup guide](/channels/guide)

## Builds and environments

**Builds** are versioned, deployable artifacts (agent graphs, tools). **Environments** (Dev, UAT, Prod) control where builds run.

- [Ship — builds and environments](/builds/guide)

## Agent Registry (A2A)

The **Agent Registry** publishes agent graphs as discoverable **Agent Cards** over the [Agent-to-Agent (A2A) protocol](https://a2a-protocol.org/latest/specification/). Use it to expose agents externally, browse the workspace catalog, compose registry agents on the canvas, or call agents from Claude.

- [Agent Registry overview](/agent-registry/overview)
- [Publish and endpoints](/agent-registry/publish)
- [Compose on canvas](/agent-registry/compose)
- [Invoke from Claude](/agent-registry/invoke-a2a-from-claude)
