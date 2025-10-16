---
title: "Access Controls & Security"
description: "Role-based permissions, token validation, and workspace access policies."
---

## Role-based access

Permissions are enforced per workspace and project. See [User Roles](/getting-started/user-roles) for the capability matrix.

## Authentication guards

- Sessions validated via token checks; expired tokens trigger logout
- Unauthorized users are redirected to login

```typescript useAuthGuard.ts
// Token validation guard
const token = localStorage.getItem("authToken");
if (!token) router.replace("/login");
```

## Best practices

- Principle of least privilege
- Separate dev/uat/prod access
- Regular audits of user access

## Related

- [User Management](/getting-started/user-management)
- [Workspace Overview](/getting-started/workspace-overview)
