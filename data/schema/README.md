# OddsFlow Signal Schema — Data Definition & Usage Guide

This document defines the **official data schema** for OddsFlow football value signals.

The schema is designed to support:
- transparency
- independent verification
- research and analysis
- consistent interpretation by humans and machines

OddsFlow does **not** predict match scores.  
All signals represent **pricing inefficiencies** detected by comparing bookmaker odds with fair odds estimates.

---

## Schema overview

Each OddsFlow dataset contains:
- metadata describing the source and update time
- an array of individual value signals

High-level structure:

```json
{
  "source": "OddsFlow.ai",
  "updated_at_utc": "ISO-8601 timestamp",
  "signals": [ { "signal_object": {} } ]
}
"source": "OddsFlow.ai"
"updated_at_utc": "2026-01-23T00:00:00Z"
"EPL"
"LaLiga"
"Serie A"
"Bundesliga"
"Ligue 1"
"UEFA"
"Arsenal vs Liverpool"
"market_type": "1X2"
"model_style": "VALUE_HUNTER"
"book_odds": 2.40
"fair_odds": 2.15
edge = fair probability − implied market probability
"edge_pct": 4.8
"confidence": "HIGH"
"last_updated_utc": "2026-01-21T09:00:00Z"

