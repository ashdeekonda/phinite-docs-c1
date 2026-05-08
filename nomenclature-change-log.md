# Nomenclature Change Log

This file tracks terminology changes applied across docs content, navigation labels, and URL/path references where those terms appeared in text/config values.

## Replacement Rules

- Flow Studio -> Graph Studio
- Agent Blocks -> Agent Nodes
- Agent Block -> Agent Node
- Master Blocks -> master nodes
- Master Block -> master node
- Child Blocks -> Child nodes
- Child Block -> Child node
- Flows -> Agent Graphs
- Flow -> Agent Graph

## Totals by Rule

- Agent Block -> Agent Node: 8
- Agent Blocks -> Agent Nodes: 1
- Flow -> Agent Graph: 47
- Flows -> Agent Graphs: 31

## Files Updated

- `.cursor/nav.md`
  - Agent Block -> Agent Node: 1
  - Flow -> Agent Graph: 1
  - Flows -> Agent Graphs: 2
- `assistants/components.md`
  - Flows -> Agent Graphs: 3
- `assistants/components/flows.md`
  - Agent Blocks -> Agent Nodes: 1
  - Flow -> Agent Graph: 3
  - Flows -> Agent Graphs: 5
- `assistants/components/intents.md`
  - Flow -> Agent Graph: 1
  - Flows -> Agent Graphs: 2
- `assistants/components/triggers.md`
  - Flow -> Agent Graph: 1
  - Flows -> Agent Graphs: 1
- `assistants/conversational.md`
  - Flows -> Agent Graphs: 1
- `assistants/overview.md`
  - Flow -> Agent Graph: 2
  - Flows -> Agent Graphs: 2
- `assistants/types.md`
  - Flows -> Agent Graphs: 1
- `builds/overview.md`
  - Flows -> Agent Graphs: 1
- `builds/publishing.md`
  - Flows -> Agent Graphs: 1
- `devstudio/system-tool.mdx`
  - Flow -> Agent Graph: 7
- `docs-1.json`
  - Agent Block -> Agent Node: 1
- `docs.json`
  - Agent Block -> Agent Node: 1
- `graph-studio/agent-node.md`
  - Agent Block -> Agent Node: 1
- `graph-studio/nodes.md`
  - Flow -> Agent Graph: 1
- `graph-studio/capture-variables-in-agent-node.mdx`
  - Agent Block -> Agent Node: 1
- `graph-studio/input-variables-in-agent-node.mdx`
  - Agent Block -> Agent Node: 3
  - Flow -> Agent Graph: 2
- `graph-studio/interface/node-library.md`
  - Flow -> Agent Graph: 1
- `graph-studio/interface/canvas.md`
  - Flow -> Agent Graph: 1
- `graph-studio/interface/inspector-panel.md`
  - Flow -> Agent Graph: 1
- `graph-studio/manual-method.md`
  - Flow -> Agent Graph: 1
- `graph-studio/overview.md`
  - Flow -> Agent Graph: 1
  - Flows -> Agent Graphs: 4
- `graph-studio/publishing.md`
  - Flow -> Agent Graph: 13
  - Flows -> Agent Graphs: 1
- `getting-started/about-phinite.md`
  - Flow -> Agent Graph: 1
- `getting-started/what-you-can-build.md`
  - Flow -> Agent Graph: 1
  - Flows -> Agent Graphs: 1
- `index.md`
  - Flows -> Agent Graphs: 2
- `reference/glossary.md`
  - Flow -> Agent Graph: 1
- `setup-account/workspace-overview.md`
  - Flows -> Agent Graphs: 1
- `support-chatbot-knowledge-rack.md`
  - Flow -> Agent Graph: 1
- `triggers-intents/intent-as-api.mdx`
  - Flow -> Agent Graph: 2
- `triggers-intents/triggers/bg_task.mdx`
  - Flow -> Agent Graph: 4
- `triggers-intents/triggers/cron.mdx`
  - Flows -> Agent Graphs: 1
- `user-management/user-roles.md`
  - Flows -> Agent Graphs: 2
- `workspaces/workspace-overview.md`
  - Flow -> Agent Graph: 1

---

## Phase 2 — URL / filesystem slugs and product naming

**Date:** 2026-05-09  

**Constraint:** The `flowgen` path prefix was renamed using the whole token `flowgen` → `graph-studio`, not by rewriting the substring `Flow` inside the product name. That avoids erroneous strings such as “Agent Graphgen”.

### Directory and file moves

| Before | After |
|--------|--------|
| `flowgen/` | `graph-studio/` |
| `flowgen/blocks/` | `graph-studio/nodes/` |
| `flowgen/blocks.md` | `graph-studio/nodes.md` |
| `flowgen/agent-block/` | `graph-studio/agent-node/` |
| `flowgen/agent-block.md` | `graph-studio/agent-node.md` |
| `flowgen/interface/block-library.md` | `graph-studio/interface/node-library.md` |
| `flowgen/blocks/master-agent.md` | `graph-studio/nodes/master-node.md` |
| `flowgen/blocks/child-agent.md` | `graph-studio/nodes/child-node.md` |
| `flowgen/blocks/tool-block.md` | `graph-studio/nodes/tool-node.md` |
| `flowgen/blocks/end-block.md` | `graph-studio/nodes/end-node.md` |
| `flowgen/input-variables-in-agent-block.mdx` | `graph-studio/input-variables-in-agent-node.mdx` |
| `flowgen/capture-variables-in-agent-block.mdx` | `graph-studio/capture-variables-in-agent-node.mdx` |

### Config / navigation

- `docs.json`: top-level group **“Flowgen Studio (Workflow Builder)”** → **“Graph Studio (Workflow Builder)”**; nested **“Blocks”** → **“Nodes”**; all `flowgen/...` page paths → `graph-studio/...` with the slugs above.
- `docs-1.json`: same path updates; commented **“Flowgen templates”** → **“Graph Studio templates”**.

### In-content link rewrites

Every `*.md`, `*.mdx`, `*.json`, and `*.txt` reference to old paths (e.g. `/flowgen/...`, `` `flowgen/...` ``) was updated to `/graph-studio/...` and the new slugs (`nodes`, `node-library`, `agent-node`, variable page names, etc.), including `index.md`, `.cursor/nav.md`, `link-audit-report.txt`, and `support-chatbot-knowledge-rack.md`.

### Product name in prose (Graph Studio)

Standalone **Flowgen** / **FlowGen Studio** / **Flowgen Studio** in documentation was normalized to **Graph Studio** via explicit multi-token replacements and word-boundary rules (not global `Flow` → `Agent Graph` on “Flowgen”). **FlowGen logic** (concept) was updated to **Agent Graph logic** where it denoted orchestration behavior.

### Corrections from over-broad “Flow” → “Agent Graph” substitutions

- Restored **React Flow** as the canvas library name in `graph-studio/overview.md` and `graph-studio/interface/canvas.md` (replacing erroneous “React Agent Graph”).
- Assistant Graphs hero image in `assistants/components/flows.md` now points at `/images/Flow.png` (fixes a broken path introduced when a filename contained “Flow”).
