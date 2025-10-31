---
title: "Microsoft Teams"
description: "Connect your agentic chatbot to Microsoft Teams."
icon: "microsoft"
---

## Connecting Your Agentic Bot to Microsoft Teams

Your chatbot can:
- Respond to Teams users
- Send proactive updates
- Provide support in Teams

---

### Step 1: Create a New Configuration

Integrations → Teams → ➕ Add Configuration → fields:
- Microsoft App ID
- Microsoft App Password
- Microsoft Tenant ID
- (Optional) Channel ID, Conversation ID
- Configuration Name

---

### Step 2: Register the bot in Microsoft Azure

1. Azure Portal → App registrations → + New registration
2. Fill:
   - Name: Agentic Bot for Teams
   - Supported accounts: Any org + personal
   - Redirect URI: if applicable
3. Register, then copy:
   - Application (Client) ID → Microsoft App ID
   - Directory (Tenant) ID → Microsoft Tenant ID

---

### Step 3: Create a Client Secret (App Password)

Certificates & secrets → + New client secret → copy Value immediately → store securely → paste into config.

---

### Step 4: Save and get Webhook URLs

On Save, Webhook URLs are generated for DEV/UAT/PROD.

Example:
```bash
https://api-server-dev.yourdomain.ai/teams/xxxxxxxx/development
```

---

### Step 5: Connect Webhook to your Bot

Paste the environment-specific Webhook URL into your Bot Framework → Messaging Endpoint → Save.

---

### Proactive messages (optional)

Add either `channelId` (for channels) or `conversationId` (for personal 1:1) into the configuration.

To get IDs:
- Message bot `getchannelid` → bot replies with `channelId`
- Message bot `getconversationId` → bot replies with `conversationId`


