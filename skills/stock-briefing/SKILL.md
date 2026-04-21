---
name: stock-briefing
description: Generate and deliver Pat's daily stock market briefing. Runs financial analysis on watchlist stocks, scores moat ratings, and delivers a structured morning briefing via Telegram.
emoji: 📊
---

# Stock Briefing Skill

Reads the daily briefing file and delivers it to Pat via Telegram. Also runs the briefing script if data needs refreshing.

## Briefing File Location
`~/.openclaw/workspace/stock-analysis/output/briefings/YYYY-MM-DD.md`

## How to Run

### Option 1: Read Existing Briefing
Read the most recent briefing file and send it to Pat:
```
Read ~/.openclaw/workspace/stock-analysis/output/briefings/YYYY-MM-DD.md
```
Then send Pat a summary in Telegram.

### Option 2: Generate Fresh Briefing
If data might be stale (>24h), run the briefing script:
```
/usr/bin/python3 ~/.openclaw/workspace/stock-analysis/scripts/daily_briefing.py
```
Then read and deliver the output.

### Option 3: Run Financials Only (no briefing)
To refresh financial data without full briefing:
```
/usr/bin/python3 ~/.openclaw/workspace/stock-analysis/scripts/financials.py
```

## Briefing Content
- Live price data (end of day previous trading day or pre-market)
- Moat scores (0-125) across 5 dimensions
- BUY/HOLD/REVIEW/SELL action per stock
- ROIC, Gross Margin, revenue growth
- Thesis checklist for follow-up

## Cron Setup (6:30 AM Melbourne time)
```
30 6 * * 1-5 /usr/bin/python3 /Users/WazzaP/.openclaw/workspace/stock-analysis/scripts/daily_briefing.py >> /Users/WazzaP/.openclaw/workspace/stock-analysis/logs/cron.log 2>&1
```
