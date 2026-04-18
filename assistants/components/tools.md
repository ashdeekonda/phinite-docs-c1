---
title: "Tools"
description: "External actions your assistants can call to get work done."
---

## Overview

<Frame>
  ![Tools 1](/images/Tools-1.png)
</Frame>

Tools are modular logic units that developers maintain and reuse across Assistants. Tools are built and versioned in [DevStudio](/devstudio/overview). Agents invoke tools to perform actions.

### Tool Types

- **API Tools** — connect to external services.
- **Logic Tools** — handle data transformations or business rules.
- **Utility Tools** — manage internal operations (e.g., token validation).

### Managed in DevStudio

Developers can:

- Edit and test tools in isolation.
- Save tools to the **Workspace Library** for reuse.
- Version and publish them for other assistants.

<info>
  Tools used in multiple assistants should always be version-controlled.\
  Breaking changes must be tested in Dev before UAT or Prod.
</info>

## Structure

- Parameters and input validation
- Return schema and capture variables
- Versioning and publishing

## Best practices

- Defensive error handling
- Secure authentication
- Clear parameter docs and examples