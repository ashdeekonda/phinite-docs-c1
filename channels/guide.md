---
title: "Channels setup guide"
description: "Configure channels for chat, voice, and email — webchat, WhatsApp, Slack, Teams, Twilio, and email."
icon: "bolt"
---

import { Lightning } from "phosphor-react";

## <Lightning weight="regular" size={24} style={{ display: 'inline', verticalAlign: 'middle', marginRight: '8px' }} />
 Features

Channels are where end users talk to your assistants. Integrations connect assistants to external systems via tools in [DevStudio](/devstudio/overview).

<Frame>
  ![channels](/images/Channels.png)
</Frame>

**Supported channels:** Web Chat, WhatsApp, Slack, Microsoft Teams, Twilio Voice, Email.

**Pre-built integrations:** Gmail, Google Sheets, Jira/Zendesk. Custom integrations are built as tools in DevStudio.

After setup, use [Testing Conversations](/triggers-intents/testing-intents) to validate channel behavior before going live.

<a id="webchat"></a>

## Webchat
<Frame>
  <img src="/images/webchat.png" alt="Web chat embed configuration" />
</Frame>

<Steps>
  <Step title="Enable web chat">
    Add the embed script to your site.
  </Step>
  <Step title="Configure appearance">
    Set colors, logo, and position.
  </Step>
  <Step title="Connect assistant">
    Select the assistant and environment.
  </Step>
</Steps>

<Note>
  Test in Dev before enabling for users.
</Note>

<a id="whatsapp"></a>

## WhatsApp
<Frame>
  <img src="/images/chatbot-integration.png" alt="WhatsApp channel integration" />
</Frame>

<Steps>
  <Step title="Obtain credentials">
    Set up WhatsApp Business API credentials.
  </Step>
  <Step title="Configure webhook">
    Point inbound messages to your channel endpoint.
  </Step>
  <Step title="Map to assistant">
    Select assistant and environment.
  </Step>
</Steps>

<Warning>
  Verify webhook signatures to prevent spoofing.
</Warning>

<a id="slack"></a>

## Slack
<Frame>
  <img
    src="/images/slack.png"
    alt="Slack integration configuration"
    style={{ width:"100%" }}
  />
</Frame>

Once connected, your bot can:

- Reply to Slack users in real time
- Send automated updates or alerts
- Handle customer support directly from Slack

### Step 1: Create a new Slack configuration

1. Integrations → Slack
2. Click ➕ Add Configuration
3. Fill in:
   - Signing Secret
   - Bot User OAuth Token (SignIn Bot Token)
   - *(Optional)* Configuration name
4. Select the agent, then **Save Configuration**

On save, webhook URLs are generated for **DEV**, **UAT**, and **PROD**.

### Step 2: Create a Slack app

1. Go to [Slack API Apps](https://api.slack.com/apps) → **Create New App → From scratch**
2. Name the app and select the workspace
3. Click **Create App**

### Step 3: Generate the bot token

1. **OAuth & Permissions** → **Scopes** → **Bot Token Scopes**
2. Add recommended scopes:

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

3. **Install to Workspace** → **Allow**
4. Copy the Bot User OAuth Token (`xoxb-...`) and paste it into your configuration

### Step 4: Get the signing secret

**Basic Information** → **App Credentials** → copy **Signing Secret** → add to your configuration.

### Step 5: Link webhook URL in Slack

1. **Event Subscriptions** → **Enable Events**
2. Paste your DEV/UAT/PROD Request URL (from your saved configuration)
3. Save changes
4. Optionally add bot events (e.g., `message.channels`, `message.im`, `app_mention`)

### Summary

| Step | Action | Output |
|------|--------|--------|
| 1 | Create configuration | Saved creds + generated webhooks |
| 2 | Create Slack app | App in your workspace |
| 3 | Token + scopes | Bot token with permissions |
| 4 | Signing secret | Verified requests |
| 5 | Link webhook | Slack events flow to your bot |

### Common issues

- **Invalid Request URL:** endpoint must be HTTPS and publicly reachable
- **Token expired:** ensure tokens are not rotating unexpectedly
- **Missing permissions:** verify scopes under **Bot Token Scopes**

<a id="teams"></a>

## Microsoft Teams
Your chatbot can:

- Respond to Teams users
- Send proactive updates
- Provide support in Teams

### Step 1: Create a new configuration

Integrations → Teams → ➕ Add Configuration. Fill in:

- Microsoft App ID
- Microsoft App Password
- Microsoft Tenant ID
- *(Optional)* Channel ID, Conversation ID
- Configuration Name

### Step 2: Register the bot in Microsoft Azure

1. Azure Portal → **App registrations** → **+ New registration**
2. Fill in:
   - Name: Agentic Bot for Teams
   - Supported accounts: Any org + personal
   - Redirect URI: if applicable
3. Register, then copy:
   - **Application (Client) ID** → Microsoft App ID
   - **Directory (Tenant) ID** → Microsoft Tenant ID

### Step 3: Create a client secret (app password)

**Certificates & secrets** → **+ New client secret** → copy **Value** immediately → store securely → paste into configuration.

### Step 4: Save and get webhook URLs

On save, webhook URLs are generated for DEV, UAT, and PROD.

Example:

```bash
https://api-server-dev.yourdomain.ai/teams/xxxxxxxx/development
```

### Step 5: Connect webhook to your bot

Paste the environment-specific webhook URL into your Bot Framework → **Messaging Endpoint** → **Save**.

### Proactive messages (optional)

Add either `channelId` (for channels) or `conversationId` (for personal 1:1) into the configuration.

To get IDs:

- Message bot `getchannelid` → bot replies with `channelId`
- Message bot `getconversationId` → bot replies with `conversationId`

<a id="slack-teams"></a>

## Slack and Teams
Slack and Microsoft Teams both use environment-specific webhook URLs (DEV, UAT, PROD) generated when you save a channel configuration. Use the [Slack](#slack) and [Microsoft Teams](#teams) sections above for full setup.

### Extended Slack event configuration

After linking your webhook URL in **Event Subscriptions**, subscribe to bot events your chatbot needs:

```bash
message.channels → for public channels
message.im → for direct messages
app_mention → to respond when mentioned
```

Click **Save Changes**. Your chatbot can now listen and respond to these Slack events.

<Note>
Slack allows only one Request URL per app. Use your DEV URL while testing, then switch to PROD when ready.
</Note>

Example webhook URLs after saving a Slack configuration:

```bash
DEV: https://api-server-dev.yourdomain.ai/slack/.../development

UAT: https://api-server-dev.yourdomain.ai/slack/.../uat

PROD: https://api-server-dev.yourdomain.ai/slack/.../production
```

### Additional troubleshooting

- **Token expired:** if token rotation is enabled in Slack, tokens may expire after 12 hours. Disable token rotation for production use.
- **Invalid Request URL:** ensure the webhook URL is publicly accessible over HTTPS.

<a id="twilio"></a>

## Twilio voice
<Frame>
  <img
    src="/Twilio.png"
    alt="Twilio voice channel"
    style={{ width:"100%" }}
  />
</Frame>

<Steps>
  <Step title="Provision number">
    Obtain a Twilio phone number.
  </Step>
  <Step title="Configure webhook">
    Set voice webhook to your channel endpoint.
  </Step>
  <Step title="Connect assistant">
    Map to assistant and environment.
  </Step>
</Steps>

<Note>
  Handle DTMF and transcription as needed in your flows.
</Note>

<a id="email"></a>

## Email
<Frame>
  ![Email](/images/email.png)
</Frame>

<Steps>
  <Step title="Connect provider">
    Configure SMTP/IMAP or provider API.
  </Step>
  <Step title="Inbound routing">
    Route inbound emails to your channel endpoint.
  </Step>
  <Step title="Assistant mapping">
    Map inbound messages to assistants.
  </Step>
</Steps>

<Tip>
  Sanitize HTML and attachments before processing.
</Tip>
