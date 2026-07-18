---
title: A2A Browse and Discovery
description: Attach registry agents on the canvas — fixed Browse vs filter-based Discovery.
---

## What this is

**Registry agent nodes** let a **Master Agent** call other exposed A2A agents from your organisation or public catalog.

| Mode | Use when | Runtime |
| --- | --- | --- |
| **Browse** | You know which agent to call | Invokes one selected registration (`a2aregistryid`) |
| **Discovery** | The right agent depends on context | Master agent matches agents using saved filters at runtime |

## Where in the product

| Surface | Path |
| --- | --- |
| Graph Studio canvas | Add **agent** node under a Master Agent |
| Browse / Discovery panel | Right panel when node is unconfigured or in registry mode |
| Same catalog data | **Agent Registry** workspace page |

![Registry filters](/images/v2/a2a/05-browse-discovery.png)

## Steps — Browse

1. Open **Graph Studio** and select a **Master Agent** node.
2. Add or select an unconfigured **agent** node beneath it.
3. Open the **Browse** panel (loads `GET /a2a-registry?workspaceid=...`).
4. Search and filter agents (same dimensions as [Agent Registry](/a2a/registry)).
5. Select an agent card and review preview (hosted URL, skills, build status).
6. Add to canvas; configure exported **tools** and **env** in the **Configuration** sub-view.
7. **Save** — node stores `agent_node_type: "browse"` and `a2aregistryid`.

## Steps — Discovery

1. From the registry panel, switch to **Discovery** mode.
2. Set filters: Visibility, Deployed (Live/Test), Input/Output MIME modes, Tags, Auth.
3. Click **Save Filters** — creates a **Discovery Agent** node (`agent_node_type: "discovery"`).
4. Configure Discovery **API key** if prompted.
5. **Save** the graph.

UI note: *In Discovery Mode, the Master Agent will find and attach the agents automatically based on your filter criteria.*

## Constraints

- One **Discovery** agent connection per Master Agent at a time.
- Target agents must be **exposed** with appropriate visibility, skills, and tags.
- Browse nodes require a connected configuration (`config_id`) before publish.

## Related

- [Agent Registry](/a2a/registry)
- [Agent Card identity](/a2a/agent-card-identity)
- [Node types](/studio/nodes)
- [Build export](/configure/build-export)
