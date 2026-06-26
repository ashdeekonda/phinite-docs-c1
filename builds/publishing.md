---
title: "Publishing Agent Graphs & Tools"
description: "Save agent graph versions and deploy safely via release builds."
---

In **Graph Studio**, click **Save as Version** on your agent graph to create a numbered version with notes. Use the toolbar **Create a release build** action to package that version for deployment, or open the assistant **Deploy** section and click **Create Build** to assemble a build from saved agent graph and tool versions.

## Steps

<Steps>
<Step title="Validate">
  Ensure all checks pass (lint, tests, validations).
</Step>
<Step title="Save as Version">
  Save the agent graph version and document changes for auditing.
</Step>
<Step title="Create and assign build">
  Create a release build from Graph Studio or **Create Build** on Deploy, then **Assign Build** to the target environment.
</Step>
</Steps>

<Warning>
Production deployments require Admin or SuperAdmin role.
</Warning>
