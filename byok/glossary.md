---
title: "BYOK glossary"
description: "Terms, UI labels, API fields, and permissions for Model Keys and Bring Your Own Key."
icon: "book-open"
sidebarTitle: "Glossary"
---

## Product terms

| Term | Meaning |
| ---- | ------- |
| **Model Keys** | Workspace page and sidebar label for BYOK |
| **Bring Your Own Key (BYOK)** | Feature: use your provider credentials for inference |
| **Phinite Key** | Built-in platform-managed credentials (`phinite-provider`) |
| **Change model** | Graph Studio modal to set resource, operation, model, and key on an agent node |
| **Model Provider Key** | A saved workspace credential for one provider |

## Graph Studio fields

| UI label | Stored as |
| -------- | --------- |
| Resource | `resource` (modality) |
| Operation (Generate / Analyze) | `operation` |
| Model | `modelName` |
| Bring your own key (BYOK) | `developMode`: `phinite` or `self` |
| Select Your Key (BYOK) | `byokid` |

## API and database

| Field | Description |
| ----- | ----------- |
| `byokid` | Unique key identifier |
| `workspaceid` | Workspace scope |
| `organizationid` | Organisation scope |
| `provider` | Catalog provider id |
| `value` | Encrypted credential |
| `isDefault` | Workspace default key |
| `ownKey` | Billing flag on usage events |
| `byokConfig` | Per-model credential field schema |

## Permissions

| Layer | Module |
| ----- | ------ |
| API | `workspace.byok` |
| Model Keys UI | `workspace.api_keys` |
| Sidebar | `workspace.sidebar.api_keys` |

## Related

- [BYOK overview](/byok/overview)
- [Access Controls](/user-management/access-controls)
