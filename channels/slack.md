---
title: Slack
description: Connect Slack as a channel for Conversational Agent Graphs.
icon: "slack"
---

<Note>
  Slack configurations generate **DEV**, **UAT**, and **PROD** webhook URLs. Assign an **Agent Build** via **Deploy to Channel** after credentials are saved in **Integrations**.
</Note>

Once connected, your Agent Graph can reply in Slack channels and DMs, send proactive updates, and handle support conversations from the workspace.

<Frame caption="Slack integration configuration form">
  <img src="/images/slack.png" alt="Slack channel configuration in Integrations" />
</Frame>

## Connect Slack

### 1. Create a Slack configuration in Phinite

1. Open **Integrations** → **Slack**.
2. Click **Add Configuration**.
3. Fill in **Signing Secret** and **Bot User OAuth Token** (`xoxb-...`).
4. Optionally set a configuration name.
5. Click **Save Configuration** — webhook URLs appear for **DEV**, **UAT**, and **PROD**.

### 2. Create a Slack app

1. Go to [Slack API Apps](https://api.slack.com/apps) → **Create New App** → **From scratch**.
2. Name the app and select the workspace.
3. Click **Create App**.

### 3. Generate the bot token

1. **OAuth & Permissions** → **Bot Token Scopes** — add:

```bash
chat:write
channels:read
channels:history
im:read
im:history
users:read
files:read
files:write
```

2. **Install to Workspace** → **Allow**.
3. Copy the **Bot User OAuth Token** → paste into Phinite **SignIn Bot Token**.

### 4. Add the signing secret

1. **Basic Information** → **App Credentials**.
2. Copy **Signing Secret** → paste into Phinite.

### 5. Link the webhook URL

1. **Event Subscriptions** → enable events.
2. Paste the **DEV** Request URL from Phinite (use DEV first; switch to PROD when ready).
3. Save — Slack verifies the endpoint.
4. Under **Subscribe to bot events**, add `message.channels`, `message.im`, `app_mention` as needed.

### 6. Deploy your Agent Graph

1. **Save** the Conversational Agent Graph and create an **Agent Build**.
2. **Deploy** → **Deploy to Channel** — select Slack, assign build to **DEV**.
3. Message the bot to test; promote to **UAT** / **PROD** when validated.

| Step | Action | Output |
| --- | --- | --- |
| 1 | Create configuration | Saved creds + generated webhooks |
| 2 | Create Slack app | App in workspace |
| 3 | Token + scopes | Authenticated bot |
| 4 | Signing secret | Verified requests |
| 5 | Link webhook | Events flow to Phinite |
| 6 | Deploy build | Agent Graph runs on messages |

<Tip>
  Slack allows one Request URL per app. Use **DEV** during development; update to **PROD** before go-live.
</Tip>

### Common issues

- **Invalid Request URL** — endpoint must be HTTPS and publicly reachable.
- **Token expired** — disable token rotation for production or refresh tokens.
- **Missing permissions** — verify scopes under **Bot Token Scopes**.

## Related

- [Deploy to channel](/agents/deploy-channel)
- [Slack / Teams combined guide](/channels/slack-teams)
- [Supported channels](/channels/supported)
