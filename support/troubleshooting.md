---
title: "Troubleshooting"
description: "Error codes, build failures, environment issues, and how to contact support."
---

<a id="error-codes"></a>

## Error codes
### Common errors

- **401 Unauthorized** — check token and roles
- **403 Forbidden** — insufficient permissions
- **404 Not Found** — resource missing or ID incorrect
- **422 Validation Error** — fix invalid inputs
- **500 Server Error** — check logs and retry

### Debugging steps

1. Reproduce with sample input
2. Check [Session Logs](/observability/logs)
3. Inspect tool/flow configuration
4. Verify environment and credentials

<Tip>
Include input, expected output, and actual error when reporting issues.
</Tip>

<a id="build-failures"></a>

## Common build failures
### Frequent issues

- Missing required fields in flows/tools
- Tool tests failing in target environment
- Version notes missing

### Resolution checklist

<Check>
- [ ] Validate all flows and tools
- [ ] Run tests with real inputs
- [ ] Add version notes
- [ ] Verify credentials per environment
</Check>

<a id="env-issues"></a>

## Environment misconfigurations
### Symptoms

- Works in Dev, fails in UAT/Prod
- Authentication errors only in one environment

### Checklist

- Separate credentials and endpoints
- Feature flags per environment
- Network egress and firewall rules

<Tip>
Log environment variables used (excluding secrets) to verify configuration.
</Tip>

<a id="contact"></a>

## Contacting support
### Before contacting support

- Collect logs and error codes
- Include sample inputs and expected outputs
- Specify environment and versions

### Contact

- Email: support@phinite.example
- Portal: https://support.phinite.example

<Note>
Include steps to reproduce to speed up resolution.
</Note>
