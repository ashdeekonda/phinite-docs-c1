---
title: "MongoDbTool"
description: "MongoDB CRUD, aggregation, indexes, and database operations for Agent Graph tools."
icon: "database"
---

**MongoDbTool** exposes database operations to Agent Graph nodes that need structured data access during a run.

<Card title="Predefined tools hub" icon="plug" href="/devstudio/prebuilt-tools">
  Operational notes for all prebuilt integrations.
</Card>

## Required configuration

| Field | Type | Notes |
| --- | --- | --- |
| `connection_string` | string | MongoDB URI (`mongodb+srv://…` or `mongodb://…`) |
| `database_name` | string | Default database for the connection |

## Setup

1. Create a least-privilege MongoDB user (avoid admin roles for app graphs).
2. Add **MongoDbTool** on an agent node and save a connection with URI + database name.
3. Test `list_collections` or `count_documents` with a narrow query.
4. Enable only required subtools; require human approval for destructive ops in prompts.

## Subtools (high level)

Insert/find/update/delete (single and many), `count_documents`, `aggregate_documents`, collection and index management, database stats/list/create/drop.

<Warning>
  `drop_collection`, `drop_database`, and heavy aggregations can impact production clusters—gate them with explicit agent instructions and QA review.
</Warning>

<Note>
  Transactions require replica-set clusters. Document whether your connection supports multi-document transactions before relying on them in graphs.
</Note>
