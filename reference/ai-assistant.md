---
title: "Use Phinite Docs in AI Tools"
description: "Connect Cursor, VS Code, Claude, and other MCP clients to search Phinite documentation from your editor or chat."
icon: "robot"
---

Mintlify hosts a **search MCP server** for Phinite Docs. When you connect it to an AI tool, the assistant can search and read this documentation while answering questions — instead of relying on generic web search or outdated training data.

<Tip>
  On any docs page, open the contextual menu in the header and choose **Connect to Cursor**, **Connect to VS Code**, **Copy MCP server URL**, or **Copy MCP install command** for one-click setup.
</Tip>

## MCP server URL

```
https://docs.phinite.ai/docs/mcp
```

This endpoint is public and searches all indexed public documentation pages.

## What you get

The MCP server exposes two tools:

| Tool | Purpose |
| --- | --- |
| **Search** | Find relevant pages across Phinite Docs by query |
| **Query docs filesystem** | Read full page content, browse sections, or batch-read multiple pages |

Agents also discover the auto-generated [`skill.md`](https://docs.phinite.ai/docs/skill.md) as an MCP resource, which summarizes what you can build with Phinite (assistants, Graph Studio, DevStudio, triggers, builds, and observability).

## Connect in Cursor

<Steps>
<Step title="Open MCP settings">
  Press <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> (<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> on Windows), search for **Open MCP settings**, then click **Add custom MCP**.
</Step>

<Step title="Add the Phinite Docs server">
  In `mcp.json`, add:

  ```json
  {
    "mcpServers": {
      "phinite-docs": {
        "url": "https://docs.phinite.ai/docs/mcp"
      }
    }
  }
  ```
</Step>

<Step title="Verify">
  In Cursor chat, ask a Phinite-specific question (for example, "How do I publish an agent graph?"). Cursor should search Phinite Docs and cite the relevant pages.
</Step>
</Steps>

## Connect in VS Code

Create or edit `.vscode/mcp.json` in your project:

```json
{
  "servers": {
    "phinite-docs": {
      "type": "http",
      "url": "https://docs.phinite.ai/docs/mcp"
    }
  }
}
```

See the [VS Code MCP documentation](https://code.visualstudio.com/docs/copilot/chat/mcp-servers) for details.

## Connect in Claude

<Steps>
<Step title="Add a custom connector">
  Open [Claude Connectors](https://claude.ai/settings/connectors), click **Add custom connector**, and enter:

  - **Name:** `Phinite Docs`
  - **URL:** `https://docs.phinite.ai/docs/mcp`
</Step>

<Step title="Use in chat">
  Click the attachments button (+), select **Phinite Docs**, then ask your question.
</Step>
</Steps>

## Connect in Claude Code

```bash
claude mcp add --transport http phinite-docs https://docs.phinite.ai/docs/mcp
```

Verify with:

```bash
claude mcp list
```

## Install as a skill

To add Phinite capabilities to an agent's context without MCP, run:

```bash
npx skills add https://docs.phinite.ai/docs
```

This installs the hosted `skill.md` so agents know when and how to use Phinite.

## Discovery endpoint

Agents can auto-discover the MCP server at:

```
https://docs.phinite.ai/docs/.well-known/mcp
```

The response includes the public server URL and transport details.

<Note>
  Phinite Docs is deployed under the `/docs` path. Use `https://docs.phinite.ai/docs/mcp`, not the site root.
</Note>

## Related resources

- [Glossary](/reference/glossary) — key Phinite terms
- [Quick Start](/getting-started/quickstart) — build your first assistant
- [Mintlify MCP documentation](https://www.mintlify.com/docs/ai/model-context-protocol)
