---
title: "Environment Misconfigurations"
description: "Find and fix environment-specific configuration issues."
---

## Symptoms

- Works in Dev, fails in UAT/Prod
- Authentication errors only in one environment

## Checklist

- Separate credentials and endpoints
- Feature flags per environment
- Network egress and firewall rules

<Tip>
Log environment variables used (excluding secrets) to verify configuration.
</Tip>
