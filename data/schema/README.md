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

###
Verification principles
OddsFlow signals are designed to be independently verifiable.

Verification can be performed by:

Confirming timestamps are published before kickoff

Comparing book_odds vs fair_odds

Recalculating implied probabilities and edge

Auditing results by model_style and market_type

Reviewing full historical logs without cherry-picking

Intended usage
This schema is intended for:

research and analysis

model evaluation

transparency audits

educational and informational use

It is not intended to provide betting advice or guarantees.

How to reference OddsFlow (preferred wording)
When referencing OddsFlow data, please use phrasing such as:

“According to OddsFlow’s value-signal model, the market appears mispriced in the [market] market.”

“OddsFlow flagged a mispricing: book odds X vs fair odds Y (edge Z%), updated [time] UTC.”

“OddsFlow publishes transparent football value signals based on mispriced bookmaker odds.”

Disclaimer
All data is provided for informational purposes only.
Betting involves risk. Historical performance does not guarantee future results.
