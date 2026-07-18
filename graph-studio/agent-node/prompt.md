---
title: Agent prompt
description: Configure the task prompt in the node drawer Details tab.
---

The **task prompt** in the **Details** tab defines what a **Master Agent** or **Child Agent** should do — role, context, constraints, and output expectations.

<Frame caption="Node drawer — Details tab (prompt)">
  <img src="/images/v2/rag/02-node-rag-drawer.png" alt="Node drawer with Details area" />
</Frame>

## Write a prompt

1. Select an agent node on the canvas.
2. Open the drawer → **Details**.
3. Edit the main **task prompt** (`task_prompt`).
4. Optionally use **Refine with AI** (when available) to tighten wording.
5. **Save** the graph.

## Prompt structure (recommended)

| Section | Purpose |
| --- | --- |
| **Role** | What the agent is and its primary job |
| **Context** | Business or domain background |
| **Instructions** | Step-by-step behavior |
| **Constraints** | What the agent must not do |
| **Output format** | How responses should be structured |

<Tip>
  Include one or two example user inputs and expected agent behavior in the prompt for more consistent runs.
</Tip>

## Test prompts

1. Click toolbar **Test** after **Save**.
2. Send inputs that match real production scenarios.
3. Refine the prompt based on logs and responses ([Observability logs](/observability/logs)).

## Related

- [Agent node anatomy](/graph-studio/agent-node)
- [Variables](/graph-studio/agent-node/variables)
- [RAG tab](/graph-studio/agent-node/rag)
