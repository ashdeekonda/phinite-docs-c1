---
title: "A2A endpoints & lifecycle"
description: "How hosted A2A URLs are formed, test vs live behaviour, and promoting registry entries."
---

## Hosted URLs (AI Core)

The application builds A2A base URLs from **`NEXT_PUBLIC_AI_CORE_SERVER_URL`** (falling back to **`https://ai-core-dev.phinite.ai`** in development presets). Typical patterns:

```text
{base}/a2a/{flowId}/{registryId}   ← many non-live registrations
{base}/a2a/{flowId}               ← live routing omitting registry identifier
```

Treat these as contract surface for **consumers**. Always confirm behaviour for your tenant’s deployed environment—the Studio copies the authoritative string when you expose or inspect an agent.

## Registry lifecycle statuses

Statuses drive badges and catalogue queries:

| Status | User-facing implication (high level) |
| ------- | ------------------------------------ |
| **TEST** | Internal validation builds before broad discovery. |
| **LIVE** | Production-facing; influences public/catalogue listing logic. |

Promoting to live invokes **`PUT /a2a-registry/{a2aregistryid}/promote-live`** from the SPA (also reachable from Builds experiences that manage registry promotions).

## What integrators send

Agents expose **skills** metadata and expected ** MIME input/output modes**. Authentication scheme labels surfaced on the agent card correspond to schemes clients must negotiate per your organisation’s gateway policy.

Discovery copy in the Studio notes that endpoints are reachable by **A2A-compatible** agents—link out to whichever canonical protocol primer your docs team publishes.

### Code anchors

| Concern | File |
| ------- | ----- |
| URL assembly (live vs with registry ID) | `src/components/headers/canvas/BottomHeader.tsx`, `src/app/.../ModernStudio.tsx` |
| Listing & filters | `src/app/[orgName]/workspace/[workspaceId]/agent-registry/page.tsx` |
| Promote mutation | `src/redux/slices/agentRegistrySlice.ts` (`promoteToLive`) |
