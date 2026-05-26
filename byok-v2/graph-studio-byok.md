---
title: "BYOK in Graph Studio"
description: "Configure Resource, Operation, Model, and Model Keys on agent nodes using the Change model modal."
icon: "diagram-project"
---

Each agent node in Graph Studio has a **Change model** modal where you choose what model runs on that step—and whether inference uses the **Phinite Key** or a workspace Model Key you own.

## Prerequisites

Before you configure BYOK on an agent node:

- Save the agent graph you are editing in Graph Studio.
- If you plan to use BYOK, add a provider key first on [Managing Model Keys](/byok-v2/managing-model-keys). You can also add it inline from this modal using **+ Add New Key**.
- Hold permission to edit agent nodes.

## Open Change model

1. Select the **agent node** on the Graph Studio canvas.
2. In the node configuration panel, open **Change model**.

![Agent node panel entry point for Change model](/images/byok/agent-node-change-model-entry.png)

The modal title is **Change model**. Use **Cancel** to close without saving. Use **Done** to apply the configuration to the node.

## Configure Resource, Operation, and Model

These three fields appear in every mode—whether BYOK is on or off. Set them before choosing a key.

| Field | What to select |
| --- | --- |
| **Resource** | Modality for this step: text, image, video, audio, or document |
| **Operation** | **Generate** to produce output, or **Analyze** to interpret input |
| **Model** | A catalog model for the selected resource and operation |

Select **Resource** and **Operation** first. The **Model** dropdown filters to matching models. While it loads, the field shows **Loading models…**. If no model matches, you may see *No models available*.

Some resources disable **Generate** when the catalog has no generate-capable model for that combination.

## Use Phinite Key (BYOK off)

Leave **Bring your own key(BYOK)** off to use platform-managed credentials.

![Change model modal with BYOK toggle off](/images/byok/change-model-modal-phinite.png)

The toggle tooltip reads: *Leave it off to use platform-managed Phinite credentials.*

<Steps>
<Step title="Set Resource, Operation, and Model">
Complete the three fields above.
</Step>
<Step title="Save the node">
Click **Done**. The node saves with platform-managed mode and no workspace key reference.
</Step>
</Steps>

## Use your Model Key (BYOK on)

Turn **Bring your own key(BYOK)** on to use a workspace credential for this node.

![Change model modal with BYOK on and Select Your Key(BYOK) filled](/images/byok/change-model-modal-byok.png)

The toggle tooltip reads: *Turn on Bring your own key (BYOK) to use an API key you configure.*

Three additional fields appear below the toggle:

| Field | Placeholder states |
| --- | --- |
| **Model Provider** | *Select provider…* |
| **Model** | Filtered by provider, resource, and operation |
| **Select Your Key(BYOK)** | *Select a model provider first* → *Loading keys…* → *No keys for this provider* → *Select a key* |

<Steps>
<Step title="Set Resource, Operation, and Model">
Complete the base fields at the top of the modal.
</Step>
<Step title="Choose Model Provider">
Select the provider for this node.
</Step>
<Step title="Choose Model">
Pick a model filtered to that provider.
</Step>
<Step title="Select Your Key(BYOK)">
Choose the workspace credential for this provider. If no key exists, click **+ Add New Key**—see the next section.
</Step>
<Step title="Save the node">
Click **Done**.
</Step>
</Steps>

<Warning>
**Done** stays disabled while BYOK is on if **Model** is empty, **Model Provider** is missing, or **Select Your Key(BYOK)** has no selection.
</Warning>

## Add and test a key from Graph Studio

Click **+ Add New Key** next to **Select Your Key(BYOK)** to open the add-key panel without closing **Change model**.

![Studio add-key panel open beside the Change model modal](/images/byok/change-model-add-key.png)

<Steps>
<Step title="Enter key details">
Provide **Name of the Key**, **Select Provider**, and the credential fields for that provider.
</Step>
<Step title="Test the credential">
Click **Test**. The button shows **Testing** while the request runs. This calls the test-connection endpoint to verify the credential against AI Core before you save.
</Step>
<Step title="Save the key">
Click **Done** in the add-key panel. Confirm the toast: *Saved "{name}".*
</Step>
<Step title="Select the new key">
In **Change model**, pick the key you just saved under **Select Your Key(BYOK)**.
</Step>
<Step title="Save the node">
Click **Done** in **Change model**.
</Step>
</Steps>

![Test connection showing Testing state in the studio add-key panel](/images/byok/test-connection-studio.png)

You can also enable **Make Default Provider+Key for future** in the panel. The helper text reads: *This Provider and key will be used as default for all future agent nodes added.*

## What is saved on the node

After you click **Done** in **Change model**, the node stores:

- **BYOK off** — platform-managed mode; no workspace key reference
- **BYOK on** — your-key mode; the selected key id and the **Model**, **Resource**, and **Operation** choices

Published agent graphs carry the key reference, not the plaintext credential. At runtime Phinite decrypts the key and passes credentials to AI Core. This applies to flows invoked directly and through [Agent Registry](/agent-registry/overview).

## Before you publish

<Check>
  Every model-using agent node has a completed **Change model** configuration
  BYOK nodes have a key selected under **Select Your Key(BYOK)**, not an empty dropdown
  New keys added from the canvas were validated with **Test**
  Workspace **Default Model** on Model Keys reflects the intended default for new nodes
</Check>

See [Agent Graph publishing](/graph-studio/publishing) for the full pre-publish checklist.

## Related pages

<CardGroup cols={2}>
<Card title="Managing Model Keys" href="/byok-v2/managing-model-keys" icon="key">
Workspace key list, drawers, and default selection.
</Card>
<Card title="Agent Node" href="/graph-studio/agent-node" icon="share-nodes">
Prompts, tools, RAG, and variables on agent nodes.
</Card>
<Card title="API & permissions" href="/byok-v2/api-and-permissions" icon="plug">
Runtime key resolution and `/byok` routes.
</Card>
</CardGroup>
