---
title: Agent Card identity
description: Agent Card fields, test vs live versions, visibility, and skills.
---

## What this is

An **Agent Card** is the public **identity** of an agent exposed over A2A. Each expose action creates an **Agent Card version** tied to a **Build**. Versions start as **TEST**; **Push to Prod** promotes one version to **LIVE** (public callable URL).

## Agent Card fields

| Field | Purpose |
| --- | --- |
| **Agent Name** | Derived from Agent Graph name (read-only in wizard) |
| **Agent Description** | Summary for catalog and A2A clients |
| **Skills** | Callable capabilities with **Input Modes** / **Output Modes** (MIME types) |
| **Discoverability Tags** | Search and Discovery filter metadata |
| **Visibility** | **Public** (any valid API key) or **Organisation** (same org only) |
| **Auth Schemes** | Platform default: organisation **API key** |

Wizard copy: *Agent Card is the identity of your agent on the Internet*.

## Where in the product

| Surface | Path |
| --- | --- |
| Expose wizard step 3 | **Deploy** → **Deploy as A2A** → **Agent Card** |
| Studio sidebar | **Agent Cards** (per graph) |
| Promote | **Push To Prod** on a TEST row |

![Agent Cards](/images/v2/a2a/03-agent-card-identity.png)

## Steps — create identity (TEST)

1. **Build** and **Save** your Agent Graph.
2. Click **Deploy** → **Deploy as A2A** (or expose from Agent Builds).
3. Complete build config and optional [export](/configure/build-export).
4. On **Agent Card** step, edit description, add **Skills**, **Tags**, and **Visibility**.
5. Optional: **Refine Card** (AI assist for description/skills).
6. Submit — version is created with status **TEST**.

## Steps — promote to LIVE

1. Open Studio → **Agent Cards** (or workspace flow for your graph).
2. Select the **TEST** version to promote.
3. Click **Push To Prod**.
4. Confirm — version becomes **LIVE**; previous LIVE for same graph demotes to TEST.

## Related

- [Expose as A2A](/agents/expose-a2a)
- [A2A endpoints](/a2a/endpoints)
- [Agent Registry](/a2a/registry)
- [Build export](/configure/build-export)
