---
title: "Expose your flow as an agent"
description: "Register a Graph Studio flow in the Agent Registry and publish metadata for A2A clients."
---

## Prerequisites

- A **published build** you can expose (the Studio surfaces **Expose as external agent** once publishing requirements are satisfied—see **[Publishing](/graph-studio/publishing)**).
- **Developer** permissions for graph tooling and gateway actions (agent registration calls the **`/a2a-registry`** API through the gateway).

## Open the wizard

From **Graph Studio**, use **Expose as external agent** in the canvas header tooling. The wizard collects the **agent card** details that appear in Agent Registry:

- Display **name**, **description**, and optional **skills** (names, descriptions—input/output modes align with **A2A** expectations).
- **Visibility**: who can discover the listing (for example scoped to organisation until you promote broadly).
- **Authentication schemes**: what callers present (for example API key); the wizard enforces picking supported schemes where required by the specification.

Behind the scenes, the UI calls **`POST /a2a-registry`** with payload constructed in `ExposeAsExternalAgentWizard` (see codebase reference below).

## After registration

When creation succeeds:

- Note the **Agent Registry ID** and the **`/a2a/`** hosted URL—the app shows URLs based on **`NEXT_PUBLIC_AI_CORE_SERVER_URL`** (environment-specific base).
- You can open **[Agent Registry](/agent-registry/catalog)** from the wizard link to inspect the listing.

Further refinements sometimes run through prompt refinement keyed for **`a2a`** generation—accept suggested copy when it improves skills or descriptions.

## Reference (implementation)

For field-level accuracy when updating screenshots or copy, align with **`flow-gen-frontend`**:

- `src/components/headers/canvas/ExposeAsExternalAgentWizard.tsx`
- `src/redux/slices/agentWizardSlice.ts` (`registerAgent`, `fetchRegisteredAgent`)
