# HEARTBEAT.md

```json
{
  "lastChecks": {
    "email": null,
    "calendar": null,
    "stocks": null,
    "memory": null,
    "academic": null,
    "heartbeatCount": 0
  }
}
```

## Rotating Check System

Rotate through checks so nothing gets starved. After every heartbeat, move to the next check in rotation:

**Order:**
1. **Email** — urgent unread messages
2. **Calendar** — events in next 24-48h
3. **Stocks** — watchlist thesis check (price moves >5%, news)
4. **Memory maintenance** — review daily log, check for stale items
5. **Academic** — deadlines within 72h

## Heartbeat Tasks

When triggered, check and act on these in priority order:

1. **MEMORY.md bottlenecks** — is the current priority still valid? Any blockers stale?
2. **Academic deadlines** — any assignment/test within 48-72h not started?
3. **Stock watchlist** — any thesis invalidated or opportunity detected?
4. **Execution log** — was yesterday's plan executed? If not, flag the gap.
5. **Decisions.md** — any decisions due for review today?

## Critical: Flush Before Compaction

**MEM-02 COMPLIANCE:** If something important just happened — a decision made, a stock thesis that changed, a goal set, anything that matters — WRITE IT TO `memory/YYYY-MM-DD.md` IMMEDIATELY. Do not wait for the next heartbeat.

OpenClaw compacts sessions automatically. If I haven't written it to memory, it gets summarised and may be lost.

**Rule: If it's important, write it now. Not later.**

## When to Reach Out

- Academic deadline within 48h with no progress → interrupt
- 24h+ with no meaningful output → alert
- Stock thesis invalidated → escalate immediately
- High-quality opportunity detected → escalate immediately
- Bottleneck stale (>3 days unchanged) → question whether it's real

## When to Stay Quiet

- Late night (23:00–08:00) unless urgent
- Just ran a check <30 min ago
- No new information since last check
