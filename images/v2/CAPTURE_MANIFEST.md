# Screenshot capture manifest (Pass 1)

Source: live `flow-gen-frontend` @ `http://localhost:3000`  
Org/workspace walked: `S5M4N3M` / `aTIVxzm` (Development1)  
Date: 2026-07-19

Quiet refs only — one image per key page in Pass 1 docs.

| Step ID | File | Surface | Notes |
| --- | --- | --- | --- |
| agents.workspace | `agents/00-workspace-home.png` | Workspace Home | Agent Graphs list; Conversational / Autonomous badges |
| agents.create | `agents/01-new-agent-graph-modal.png` | New Agent Graph | Name, description, Conversational vs Autonomous only |
| studio.shell | `studio/01-studio-aura-shell.png` | Graph Studio | Aura + canvas; Save / Build / Deploy / Test |
| studio.tools | `studio/02-tools-sidebar.png` | Studio → Tools | Graph-scoped tools panel |
| builds.sidebar | `builds/01-agent-builds-sidebar.png` | Studio → Agent Builds | Empty: “use Build in the toolbar” |
| builds.prep | `builds/02-build-wizard.png` | Build prep dialog | Freeze graph + tool versions |
| builds.form | `builds/03-build-form.png` | Build Agent form | Description, AGENT GRAPH, TOOLS (+ Publish) |
| builds.env | `builds/04-env-variables.png` | Env. variables | DEV / UAT / PROD columns |
| deploy.triggers | `deploy/02-triggers-sidebar.png` | Studio → Triggers | Empty + link to Integrations |
| deploy.integ-menu | `deploy/03-integrations-menu.png` | Integrations submenu | Channels, Integration Tools |
| deploy.hub | `deploy/04-integrations-hub.png` | Integrations hub | Tabs: Tools / Channels / Triggers |
| a2a.cards | `a2a/01-agent-cards-sidebar.png` | Studio → Agent Cards | Empty until exposed |
| a2a.registry | `a2a/02-agent-registry.png` | Agent Registry | Workspace catalog |
| tools.all | `devstudio/01-all-tools.png` | Tools (`/all-tools`) | Workspace Tools list; **Open Dev Studio** / **New Tool** |

## Pass 3 captures

| Step ID | File | Surface | Notes |
| --- | --- | --- | --- |
| rag.data-sources | `rag/01-data-sources.png` | RAG Data | Workspace collections list |
| rag.node-drawer | `rag/02-node-rag-drawer.png` | Studio node drawer | RAG tab on agent node |
| studio.variables | `studio/03-variables.png` | Studio variables | Flow/session variables panel |
| studio.nodes | `studio/04-nodes-canvas.png` | Graph Studio canvas | Node graph layout |
| workspace.models | `workspace/01-model-keys.png` | Model Keys | BYOK / provider keys |
| configure.integrations | `configure/01-integrations-hub.png` | Integrations hub | Triggers tab |
| configure.build-export | `configure/02-build-export.png` | Build Agent dialog | Graph + tools pinning (export in Expose step 2) |
| a2a.identity | `a2a/03-agent-card-identity.png` | Agent Cards sidebar | Card versions for graph |
| a2a.registry | `a2a/04-registry-catalog.png` | Agent Registry | Search + filters |
| a2a.discovery | `a2a/05-browse-discovery.png` | Agent Registry | Filter UI (Browse/Discovery uses same catalog data) |

## Live UI truths (reconcile)

- Top object on Workspace Home is **Agent Graph**, not Assistant.
- Create picker: **Conversational** | **Autonomous** only. Filter still lists **Email** (legacy filter chip).
- Studio toolbar: **Save → Build → Deploy → Test**. Deploy disabled until a build exists; Build disabled until saved.
- Build freezes agent graph + tool versions; unpublished tools show **Publish**.
- Environments: **DEV / UAT / PROD** on Env. variables page.
- Conversational Deploy tabs (code): **Deploy as A2A** | **Deploy to Channel** | **Deploy as Chat API**.
- Autonomous Deploy tabs (code): **Deploy as API** | **Cron job** | **Deploy as A2A** (coming soon).
- Studio Graph assets: Graph Versions, Agent Builds, Agent Cards, Triggers, Integrations, Tools.
- Workspace nav: Workspace Home, Tools, Env. variables, Agent Registry, Integrations, MCP Server, RAG Data, Observability, Keys.
- Tools live at `/all-tools` (not labeled “DevStudio” in nav); separate from Studio Tools panel.
