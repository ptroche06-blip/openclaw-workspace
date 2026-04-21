# Warren's Stock Analysis System

AI-powered personal stock research pipeline — built by Warren (Pat's OpenClaw agent).

## What It Does

Every morning this system:
1. Pulls live price data for Pat's watchlist
2. Computes financial scores (ROIC, gross margin, revenue growth)
3. Scores moat ratings across 5 dimensions
4. Generates a structured briefing with BUY/HOLD/REVIEW actions

## The Stack

- **Language:** Python 3.9
- **Data:** Yahoo Finance (`yfinance`)
- **Data frames:** `pandas`
- **Scheduling:** OpenClaw cron + `launchd` (Mac)
- **Delivery:** Telegram (via OpenClaw)

## Project Structure

```
stock-analysis/
├── config/
│   ├── watchlist.txt          # Tickers to track (one per line)
│   └── moat_assessments.csv  # Pat's qualitative moat scores
├── scripts/
│   ├── financials.py          # Fetch + cache financial data
│   └── daily_briefing.py     # Generate daily briefing
├── data/cache/               # Cached financial CSVs
├── output/briefings/         # Daily markdown briefings
└── logs/                    # Cron logs + error logs
```

## Quick Start

```bash
# Install dependencies
pip3 install yfinance pandas numpy

# Fetch financials for watchlist
/usr/bin/python3 scripts/financials.py

# Generate briefing
/usr/bin/python3 scripts/daily_briefing.py
```

## Watchlist

Currently tracking: BHP.AX, AAPL, CBA.AX, CSL.AX, NVDA

## Moat Scoring

Stocks scored 0-125 across 5 dimensions:
1. Switching Costs (0-25)
2. Network Effects (0-25)
3. Intangible Assets (0-25)
4. Cost Advantage (0-25)
5. Financial Strength (0-25)

## Status

MVP running. Phase 2: news sentiment, technical indicators, 15-stock watchlist.

---

*Built by Warren 🐝 for Pat*
