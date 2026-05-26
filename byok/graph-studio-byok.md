---
title: "BYOK in Graph Studio"
description: "Configure model provider, resource, operation, and Model Keys on agent nodes using the Change model modal."
icon: "diagram-project"
---

## Open Change model

1. Open **Graph Studio** for your project.
2. Select an **agent node** that uses a model.
3. Open **Change model** from the node configuration.

The modal sets which model runs on this node, whether the node **generates** or **analyzes** content, and whether inference uses the **Phinite Key** or a workspace Model Key.

## Configure resource, operation, and model

| Field | Description |
| ----- | ----------- |
| **Resource** | Modality for the step: text, image, video, audio, or document |
| **Operation** | **Generate** to create output, or **Analyze** to interpret input. Some resources disable **Generate** when no generate-capable models exist. |
| **Model** | Model from the catalog for the selected resource and operation |

Select **Resource** and **Operation** before choosing **Model**. While models load, the field shows **Loading models…**.

## Use the Phinite Key (BYOK off)

Leave **Bring your own key (BYOK)** turned off to use platform-managed credentials.

The toggle tooltip states that when BYOK is off, Phinite supplies credentials. You only need to select **Resource**, **Operation**, and **Model**.

Click **Done** to save. The node stores `developMode: phinite` with no `byokid`.

## Use your own key (BYOK on)

Turn **Bring your own key (BYOK)** on. Additional fields appear:

1. **Model Provider** — provider for this node.
2. **Model** — models available for that provider and the selected resource and operation.
3. **Select Your Key (BYOK)** — workspace key for that provider.

If no key exists for the provider, click **+ Add New Key** to open the add-key panel beside the modal.

### Add and test a key on the canvas

<Steps>
<Step title="Enter key details">
Provide **Name of the Key**, **Select Provider**, and the credential fields required for the model.
</Step>
<Step title="Test connection">
Click **Test** to verify the credential against AI Core before saving. Wait for **Testing** to complete.
</Step>
<Step title="Save the key">
Click **Done** in the add-key panel. A confirmation appears when the key is saved.
</Step>
<Step title="Select the key">
In **Change model**, choose the key under **Select Your Key (BYOK)**.
</Step>
<Step title="Save the node">
Click **Done** in **Change model** to apply settings to the agent node.
</Step>
</Steps>

Optionally enable **Make Default Provider+Key for future** in the add-key panel to use this provider and key as the default for new agent nodes in the workspace.

<Warning>
**Done** in **Change model** stays disabled while BYOK is on if no model is selected, the provider is missing, or no key is selected under **Select Your Key (BYOK)**.
</Warning>

## What is saved on the node

Saving **Change model** updates `orchestration_model` on the agent block:

| Setting | Phinite Key | BYOK |
| ------- | ----------- | ---- |
| Mode | `developMode: phinite` | `developMode: self` |
| Key reference | None | `byokid` of the selected workspace key |
| Model | `modelName`, `resource`, `operation` from the modal | Same |

Published builds should reference `byokid`, not pasted secrets. At runtime, Phinite decrypts the workspace key and passes credentials to AI Core. The same resolution applies to published flows invoked through Agent Registry.

## Before you publish

<Check>
  Every model-using agent node has a completed **Change model** configuration
  BYOK nodes have a key selected, not an empty **Select Your Key (BYOK)** field
  New keys were tested with **Test** when added from Graph Studio
  Workspace **Default Model** matches your intended default for new nodes
</Check>

## Related

- [Managing Model Keys](/byok/managing-model-keys)
- [Agent Node](/graph-studio/agent-node)
- [Publishing](/graph-studio/publishing)
