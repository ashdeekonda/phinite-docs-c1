---
title: "invoke-a2a-from-claude"
---

The Phinite plugin lives in this GitHub marketplace:

> [**https://github.com/Auto-AI-Labs/phinite-plugins**](https://github.com/Auto-AI-Labs/phinite-plugins)

## Install in Cowork (desktop)

1. Open **Customize → Plugins → Personal**.
2. Click on **\+** sign.
3. Click on **Add marketplace → Add from a repository**.
4. Add a marketplace using the GitHub link above.
5. Install the **Phinite Agents** plugin.
6. Click on **Manage**
7. Open **Connectors**, click **Install → Connect**, and sign in to your Phinite account.
8. Your plugin is now ready to use — just send a request to Claude and it will find the right agent for you.

## Install in Claude Code (CLI / terminal)

```text
/plugin marketplace add Auto-AI-Labs/phinite-plugins
/plugin install phinite-agents@phinite
/reload-plugins
```

Now just send this request **Authorize phinite plugin** and sign in to Phinite when prompted.

> It's OAuth; you just sign in to your Phinite account. Now your plugin is ready to use — just send a request to Claude and it will find the right agent for you.

## Use it in Claude web (claude.ai)

On claude.ai there's no plugin marketplace — add Phinite as a **custom connector** instead:

1. Go to **Settings → Connectors → Add custom connector**.
2. Paste the Phinite MCP server URL:
   ```text
   https://phinite.ai/api/v1/ai/mcp
   ```
3. Click **Add**, then **Connect**, and sign in to your Phinite account.

---

## How to use it

Once connected, just talk to Claude — it finds the right agent, runs it, and brings back the reply:

```text
"What agents do I have?"
"Find an agent that can book my appointments"
"Ask the sales agent to qualify this lead: ..."
"Now make that shorter"
```

**Behind the scenes**, the plugin gives Claude three tools (it picks them for you):

- **`discover_agents`** — find the right agent from what you describe.
- **`list_agents`** — see every agent in your workspace.
- **`call_agent`** — Invoke an agent to perform tasks.

**Follow-ups stay in the same thread.** When you continue a conversation, Claude reuses the agent's task so it remembers the context.

**If an agent needs a tool of its own** (Gmail, Slack, a calendar, etc.), it replies with a quick **setup link**. Open it, configure your agent, what it asks for, then tell Claude to continue — the agent can now do the task.

---

_You'll need a Phinite account. Build and publish your agents at [phinite.ai](https://app.phinite.ai/sign-up)._ For builders: visibility (`public` vs `organisation`) and API key rules are documented in [Endpoints & lifecycle](/agent-registry/endpoints-and-lifecycle).

## Related pages

How the registry fits into publish and compose workflows. Workspace search and filters — the same metadata `discover_agents` uses. Hosted A2A URLs, test vs live, and authentication. A2A terms, connector tools, and UI label mapping.