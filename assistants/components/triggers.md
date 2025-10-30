---
title: "Triggers"
description: "Configure triggers to start flows automatically or from external systems."
---

# Triggers

Triggers define how and when a flow begins.\
You can configure them to start automatically, on a schedule, or through external API calls.

<Frame>
  ![Trigger](/trigger.png)
</Frame>

<Info>
  Triggers connect your assistant to external workflows and automation systems.
</Info>

---

## Trigger Types

Phinite supports three trigger types.

<Accordion title="1. API-Based Trigger">
  API-based triggers allow external applications to start a specific flow.

  **Use Case**

  - When you need real-time activation from an external event such as a form submission or webhook.

  **Configuration**

  - Requires an API key defined at the workspace level.
  - Called via an HTTP POST request.

  **Example**

  ```bash
  POST https://api.phinite.ai/trigger/<flow_id>
  Headers:
    Authorization: Bearer <workspace_api_key>
  ```

  **Best For** Fast, real-time executions where the response completes within seconds.
</Accordion>

<Accordion title="2. Scheduler-Based Trigger">
  Scheduler-based triggers start flows at fixed intervals or specific times.

  **Use Case**

  Use this for periodic automation such as daily reports, nightly data syncs, or batch processing.

  **Configuration**

  - Define a start time and recurrence (hourly, daily, weekly, or custom cron).
  - Ideal for long-running flows that might exceed API timeouts.

  **Best For**

  Background processes that do not require immediate response.
</Accordion>

### **Choose the Right Trigger**

| Scenario                                                | Recommended Trigger | Reason                                    |
| ------------------------------------------------------- | ------------------- | ----------------------------------------- |
| External app sends an event that needs immediate action | **API-Based**       | Instant activation with minimal latency   |
| Recurring process such as reports or sync tasks         | **Scheduler-Based** | Prevents timeout and automates repetition |

### Configure a Trigger

<Steps>
  <Step title="Go to Assistants → Components → Triggers.">
    
  </Step>
  <Step title="Click Create Trigger.">
    
  </Step>
  <Step title="Select the Trigger Type (API, Scheduler, or Manual).">
    
  </Step>
  <Step title="Choose the Target Flow.">
    
  </Step>
  <Step title="Set API Key or scheduling options.">
    
  </Step>
  <Step title="Save and test the trigger.">
    
  </Step>
</Steps>

<Card title="Tip">
  Use scheduler-based triggers for long-running workflows that may exceed standard API timeout limits.
</Card>

### Manage Triggers

| **Action**  | **Description**                        |
| :---------- | :------------------------------------- |
| **Edit**    | Update type, frequency, or target flow |
| **Pause**   | Temporarily disable the trigger        |
| **Run Now** | Execute immediately for testing        |
| **Delete**  | Remove from the workspace permanently  |

## Workspace API Keys

API-based triggers depend on workspace-level API keys for authentication.

<Info>
  Store and rotate keys securely. Never expose API keys in client-side or public repositories.
</Info>

### 

## **Best Practices**

- Use **API triggers** for short, transactional events.
- Use **Scheduler triggers** for background or recurring jobs.
- Avoid attaching multiple triggers to the same flow unless needed.
- Test each trigger thoroughly in the development environment before deploying to production.

## **Related Topics**

- [Intents](/assistants/components/intents)
- [Flows](/assistants/components/flows)