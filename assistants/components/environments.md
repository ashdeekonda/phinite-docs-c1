---
title: "Environments"
description: "Dev, UAT, and Production environments for deployments."
---

## Overview
Phinite offers isolated environments to safely develop and deploy.

<Frame>
  <img src="/enviroment.png" alt="Environments" />
</Frame>


### Default Environments

- **Dev** — for experimentation and iteration.
- **UAT** — for staging, pre-production testing.
- **Production** — live environment accessible to end users.

### Environment-Specific Controls

- Role-based access
- Build version mapping
- Logging and observability per environment

<Note type="tip">
  Keep tool credentials and environment variables separate across environments.\
  Avoid reusing Production keys in Dev or UAT.
</Note>

Separate environments ensure safe deployments.

- **Dev**: rapid iteration and testing
- **UAT**: stakeholder acceptance testing
- **Prod**: live users and traffic

## Best practices

- Strict access controls per environment
- Separate credentials and secrets
- Clear promotion policies