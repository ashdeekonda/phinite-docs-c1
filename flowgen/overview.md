---
title: "Flowgen Studio Overview"
description: "Build intelligent workflows with visual automation, multi-agent orchestration, and enterprise-grade debugging capabilities."
---

## What is Flowgen Studio?

Flowgen Studio is Phinite's visual workflow builder that enables you to create sophisticated AI-powered automations without coding. Design complex multi-agent systems using an intuitive canvas interface, connect them with conditional logic, and deploy with full observability and access controls.

<CardGroup cols={2}>
<Card title="Prompt-based creation (Copilot)" icon="sparkles" href="/flowgen/copilot-method">
Describe your automation goal in natural language and let AI generate the initial workflow structure.
</Card>

<Card title="Manual canvas editing" icon="pencil" href="/flowgen/manual-method">
Design precise workflows by dragging and connecting building blocks with full control over logic flow.
</Card>
</CardGroup>

## Key capabilities

### Visual workflow design
- **Drag-and-drop canvas**: Intuitive interface powered by React Flow for complex workflow visualization
- **Real-time collaboration**: Multiple team members can work on flows simultaneously with live updates
- **Version control**: Track changes, compare versions, and rollback to previous iterations

### Multi-agent orchestration
- **Master Agents**: Primary reasoning units with full access to tools, RAG, and conditional logic
- **Child Agents**: Reusable sub-workflows that can be embedded across multiple flows
- **Agent communication**: Seamless data passing and coordination between agents

### Enterprise features
- **Role-based access**: Control who can view, edit, or publish flows based on [user roles](/getting-started/user-roles)
- **Environment management**: Deploy flows across Development, UAT, and Production environments
- **Audit trails**: Complete logging of all changes, executions, and user actions

### Advanced logic & data
- **Conditional routing**: Use LLM-evaluated decision variables to create dynamic workflow paths
- **Variable management**: Capture, transform, and pass data between workflow steps
- **RAG integration**: Ground agents with enterprise knowledge from connected data sources

### Debugging & observability
- **Execution logs**: Real-time monitoring of workflow runs with detailed step-by-step traces
- **Error handling**: Comprehensive error boundaries and debugging tools for troubleshooting
- **Performance metrics**: Track execution times, success rates, and resource usage

## Prerequisites

### Access requirements
- **Workspace membership**: You must be added to a workspace with appropriate [permissions](/getting-started/access-controls)
- **Role assignment**: Minimum "Developer" role required for creating flows, "Admin" for publishing
- **Project access**: Flows are created within projects - ensure you have project-level access

### Technical setup
- **Data sources**: Configure [RAG collections](/flowgen/rag-management) if agents need enterprise knowledge
- **Tool integrations**: Set up [external APIs](/devstudio/overview) and authentication credentials
- **Environment variables**: Configure any required secrets or configuration values

## User roles and permissions

<Warning>
Flowgen Studio access is controlled by workspace-level permissions. Users without appropriate roles will see limited functionality or be blocked from accessing certain features.
</Warning>

| Role | Can Create Flows | Can Edit Flows | Can Publish Flows | Can View Logs |
|------|------------------|----------------|-------------------|---------------|
| **SuperAdmin** | ✅ | ✅ | ✅ | ✅ |
| **Admin** | ✅ | ✅ | ✅ | ✅ |
| **Developer** | ✅ | ✅ | ❌ | ✅ |
| **Tester** | ❌ | ❌ | ❌ | ✅ |
| **Viewer** | ❌ | ❌ | ❌ | ❌ |

## Getting started workflow

<Steps>
<Step title="Access Flowgen Studio">
  Navigate to your workspace → Projects → [Select Project] → Studio tab
  
  <Check>
  You should see the Flowgen Studio interface with canvas, block library, and inspector panels.
  </Check>
</Step>

<Step title="Choose creation method">
  Select either "Create with Copilot" for AI-assisted generation or "Create manually" for full control.
  
  <Tip>
  Start with Copilot for complex workflows, then refine manually for precise control.
  </Tip>
</Step>

<Step title="Design your workflow">
  Add blocks, configure agents, connect logic, and test your flow with sample inputs.
  
  <Note>
  Use the debugging tools in the bottom panel to monitor execution and troubleshoot issues.
  </Note>
</Step>

<Step title="Publish and deploy">
  Save your flow, add version notes, and publish to your target environment.
  
  <Warning>
  Only users with "Admin" or "SuperAdmin" roles can publish flows to production environments.
  </Warning>
</Step>
</Steps>

## Related concepts

- **[Building Assistants](/assistants/overview)**: Learn how flows integrate with conversational and autonomous assistants
- **[DevStudio](/devstudio/overview)**: Create custom tools that flows can utilize
- **[Observability](/observability/overview)**: Monitor flow performance and debug issues
- **[User Management](/getting-started/user-management)**: Understand workspace permissions and access controls


