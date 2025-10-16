---
title: "Event-Based Triggers (Cron, Email)"
description: "Run flows on schedules or when events occur."
---

## Types

- **Cron**: Scheduled execution (e.g., hourly sync)
- **Email**: Start on inbound emails

## Cron example

```cron
0 * * * *  # Run hourly
```

<Note>
Ensure idempotency for recurring jobs.
</Note>
