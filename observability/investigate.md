---
title: Investigate a session
description: Span, Timeline, and Conversation investigation studio with metrics, rubric, and annotations.
---

**Investigate** opens a focused studio for one observability session — deeper than the classic logs timeline.

## Open Investigate

1. Go to **OPERATE → Observability → Sessions**.
2. Open a session row, or navigate to `…/observability/{sessionId}/investigate`.
3. Chrome label: **Investigate** / page **Session investigation**.

Session detail without Investigate remains at `…/observability/{sessionId}` (**Logs**, **Back** to the call logs list) and loads `/logs-metadata`.

## View modes

| Mode | Use |
| --- | --- |
| **Span** | Span tree / inspector |
| **Timeline** | Trace waterfall over time |
| **Conversation** | Turn thread |

## Context rail tabs

| Tab | Contents |
| --- | --- |
| **Metrics** | Session/run metrics |
| **Params** | Parameters for the selected span |
| **Rubric & Feedback** | Rubric scoring / feedback |
| **Insights** | Rows such as **Workflow status**, **LLM calls**, **LLM failures**, tokens, tools, **Duration** |
| **Annotations** | Annotate modal for notes |

You can save golden material toward [Evaluations](/evaluations/run-on-draft) Production datasets where the UI offers it.

## API

```http
GET /observability/sessions/:sessionId/investigation
```

Permission: `workspace.reports.read`.

## Related

- [Insights](/observability/insights)
- [Session logs timeline](/observability/logs/timeline)
- [Run on draft](/evaluations/run-on-draft)
