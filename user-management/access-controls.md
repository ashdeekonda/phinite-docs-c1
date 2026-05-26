---
title: "Access Controls & Security"
description: "How workspace permissions and sign-in protect your organization’s work."
---

## Role-based access

Permissions apply **per workspace** (and can combine with rules elsewhere in Phinite). For what each **role** can do, see [User Roles](/user-management/user-roles).

## Sign-in and sessions

- You stay signed in while your session is valid; when it expires, sign in again.
- If you can’t reach a page you expect, your administrator may need to adjust your access.

## Best practices

- Grant people the **least access** they need for their job.
- Separate **development**, **test**, and **production** access when your organization uses multiple environments.
- Review **who has access** after role changes or when someone leaves the team.

## Model Keys (BYOK)

Workspace **Model Keys** use API permission `workspace.byok` (create, read, update, delete). The Model Keys UI also checks `workspace.api_keys` for page actions. See **[BYOK glossary](/byok/glossary)** for the full permission map.

## Related

- [User Management](/user-management/user-management)
- [Workspace Users page](/user-management/workspace-ui)
- [Workspace Overview](/workspaces/workspace-overview)
- [BYOK overview](/byok/overview)
