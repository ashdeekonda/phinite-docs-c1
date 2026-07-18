---
title: Mapping triggers to workflows
description: Assign triggers to Agent Builds and validate runs per environment.
---

**Mapping** connects a **trigger** (API, Cron, or integration webhook) to a specific **Agent Build** for each **environment**. When the trigger fires, the platform runs that pinned graph snapshot — not the live draft on the canvas.

<Note>
  Legacy docs referred to **intents**; triggers and **Agent Builds** are the current model. Validate mappings in **DEV** and **UAT** before **PROD**.
</Note>

## Map a trigger to an Agent Build

1. Open **Integrations** → **Triggers** (or Studio → **Triggers** → **Add trigger in Integrations**).
2. Create or edit the trigger — select **workflow type** (API, Background Task, Cron, or conversational variant).
3. Choose the **Agent Graph** scope if prompted (graph-scoped triggers from Studio).
4. Assign the **Agent Build** row to **DEV** first.
5. Copy the environment-specific webhook URL or Cron schedule from the trigger detail page.
6. Send a test request (API) or wait for a scheduled tick (Cron) — confirm the correct graph version in [Observability logs](/observability/logs).
7. Promote the build assignment to **UAT**, then **PROD**, when tests pass.

## Validate the mapping

1. Note the **build number** and **description** on the assigned build row ([Builds overview](/builds/overview)).
2. Invoke the trigger with a known test payload ([API usage examples](/triggers-intents/triggers/api-guide)).
3. Confirm log entries reference nodes from the expected graph version.
4. If the wrong build runs, re-open the trigger config and re-select the build for that environment.

<Check>
  Mappings should be validated in **DEV** and **UAT** before **PROD**. Keep DEV and PROD webhook URLs separate in external systems.
</Check>

## Integration funnel triggers

For Jira and similar inbound integrations, the external payload lands in `user_variables`. See [Integration funnel](/triggers-intents/triggers/integration-funnel) for endpoint shape and secret setup.

## Related

- [Deploy a trigger](/agents/deploy-trigger)
- [Trigger APIs overview](/triggers-intents/triggers/overview)
- [Build lifecycle](/builds/lifecycle)
