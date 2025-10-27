---
title: "Quick Start"
description: "Learn how to create your organization, choose a plan, invite users, and begin building agents in Phinite."
---

# Getting Started

Welcome to **Phinite** — the AI automation platform for building, deploying, and scaling multi-agent workflows across chat, voice, and enterprise systems.

This guide walks you through how to create your **Organization**, set up your **Workspace**, invite users, understand plan limits, and start your first build.

---

## 1. Create Your Organization

When you sign up for the first time, Phinite automatically creates an **Organization** for you.\
An organization defines your billing, usage, environments, and access control.

### Sign-Up Form Fields

| **Field**               | **Description**                               | **Example**        |
| ----------------------- | --------------------------------------------- | ------------------ |
| **Organization Name**   | The name of your company or project.          | `Acme Labs`        |
| **Owner Full Name**     | The legal name of the account owner or admin. | `Jane Doe`         |
| **Owner Email Address** | Used for login and notifications.             | `jane@acmelabs.ai` |
| **Password**            | Secure password for access.                   | `••••••••`         |

After completing the form:

1. **Verify your email address** to activate your account.
2. **Organization is auto-created** with default settings.
3. You are logged in as the **Super Admin**.

> 🛈 All resources, usage, and billing are tied to the organization — not the individual user.

---

## 2. Choose a Plan

Phinite offers three tiers designed for different scales of operation.

| **Capability**                           | **Free Tier**           | **Pro Plan (\$30 / mo)** | **Enterprise (Custom)** |
| ---------------------------------------- | ----------------------- | ------------------------ | ----------------------- |
| **Workspaces per Org**                   | 1                       | 3                        | Unlimited               |
| **Assistants per Workspace**             | 5                       | 5                        | Unlimited               |
| **Users per Workspace**                  | 1 (Super Admin only)    | 3                        | Unlimited               |
| **Environments**                         | Dev, Prod               | Dev, Prod                | Dev, UAT, Prod          |
| **Compute Power**                        | Basic                   | Enhanced                 | Dedicated / Unlimited   |
| **Copilot Tokens (FlowGen + DevStudio)** | Limited quota           | Enhanced quota           | Unlimited               |
| **Voice / STT / TTS Minutes**            | Limited                 | Enhanced                 | Unlimited               |
| **Support / SLA**                        | 24 hr                   | 6 hr                     | 1 hr priority           |
| **Billing Model**                        | Free                    | Monthly                  | Custom contract         |
| **Ideal For**                            | Solo creators, students | Startups & small teams   | Enterprises & OEMs      |

---

## 3. Add Users

Depending on your plan, you can invite additional team members.

### Inviting Users

1. Navigate to **Admin → User Management**.
2. Click **Invite User**.
3. Enter the email and assign a **Role** (Admin, Developer, Viewer).
4. The invite is sent via email.

### Accepting Invites

Invited users receive an email titled\
**“You’ve been invited to join [Org Name] on Phinite.”**\
They click **Accept Invite → Set Password → Verify Email** to join.

> Invites expire after 72 hours. Re-issue from the Admin dashboard if needed.

---

## 4. Workspaces

A **Workspace** is where you design, build, and deploy your AI agents.

| **Plan**   | **Workspaces**   | **Behavior**                        |
| ---------- | ---------------- | ----------------------------------- |
| Free       | 1 (auto-created) | Created automatically at sign-up    |
| Pro        | 3 max            | Admins create additional workspaces |
| Enterprise | Unlimited        | Isolated per project / environment  |

Each workspace contains:

- **FlowGen Studio** – Visual flow builder
- **DevStudio** – Tool & integration manager
- **Datasources** – Knowledge base & RAG collections
- **Environments** – Dev / UAT / Prod (per plan)
- **Observability** – Logs, sessions, and metrics

---

## 5. User Roles & Access

Roles determine what a user can do inside Phinite.

| **Role**            | **Access Level** | **Capabilities**                                      |
| ------------------- | ---------------- | ----------------------------------------------------- |
| **Super Admin**     | Full             | Manages org, billing, environments, and users.        |
| **Admin**           | Partial          | Manages workspaces & assistants; no billing access.   |
| **Developer**       | Limited          | Builds flows and tests agents in assigned workspaces. |
| **Viewer / Tester** | Read-only        | Views logs, sessions, and metrics.                    |

**Default Access by Plan**

- Free Tier → 1 Super Admin only
- Pro Plan → Super Admin + Admin/Developer roles
- Enterprise → Full hierarchy with environment-level permissions

---

## 6. Feature Limits & Quotas

| **Resource**                        | **Measured By**                  | **Limit Behavior**            |
| ----------------------------------- | -------------------------------- | ----------------------------- |
| **Compute Power**                   | Agent runtime seconds            | Requests throttled at limit   |
| **Copilot Tokens**                  | LLM usage in FlowGen / DevStudio | Paused when quota reached     |
| **Voice Minutes**                   | Call duration                    | Calls disabled after limit    |
| **STT / TTS Minutes**               | Audio processing time            | Conversion halted at limit    |
| **Workspaces / Assistants / Users** | Count                            | Creation blocked beyond limit |

View usage in **Billing → Usage Dashboard**.

---

## 7. Support & SLA

| **Plan**   | **Response Time** | **Support Channels**                  |
| ---------- | ----------------- | ------------------------------------- |
| Free       | 24 hr             | Email                                 |
| Pro        | 6 hr              | Email + Chat                          |
| Enterprise | 1 hr              | Dedicated Channel + Priority Engineer |

---

## 8. Next Steps

✅ **Quick Start Checklist**

| # | **Action**             | **Outcome**                                  |
| --- | ---------------------- | -------------------------------------------- |
| 1 | Create Organization    | Org + default workspace created              |
| 2 | Verify Email           | Account activated                            |
| 3 | Choose Plan            | Free / Pro / Enterprise features enabled     |
| 4 | Add Users              | Collaborators invited                        |
| 5 | Access Workspace       | FlowGen & DevStudio available                |
| 6 | Build Your First Agent | Deploy to Dev or Prod                        |
| 7 | Monitor Usage          | Track tokens & sessions in Billing Dashboard |

---

## Related Modules

- [User Sign-Up & Organization Setup](../organization-signup.md)
- [Workspace Overview](../workspace.md)
- [Billing Dashboard](../billing.md)
- [User Roles & Permissions](../user-roles.md)
- [Environments](../environments.md)