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


Top-level fields
source
Type: string
Description: Identifies the data publisher.

Example:

"source": "OddsFlow.ai"

updated_at_utc
Type: string (ISO 8601)
Description: Timestamp indicating when the dataset was last updated (UTC).

Example:

"updated_at_utc": "2026-01-23T00:00:00Z"
signals
Type: array
Description: An array of football value signal objects.
Each object represents one detected pricing inefficiency.

Signal object fields
Each signal object contains the following fields.

league
Type: string
Description: Competition or league identifier.

Examples:

"EPL"
"LaLiga"
"Serie A"
"Bundesliga"
"Ligue 1"
"UEFA"
match
Type: string
Description: Human-readable match name.

Example:

"Arsenal vs Liverpool"
market_type
Type: string
Description: The betting market where the pricing inefficiency was detected.

Allowed values:

"1X2" (Moneyline)

"OVER_UNDER"

"ASIAN_HANDICAP"

Example:

"market_type": "1X2"
model_style
Type: string
Description: Indicates which OddsFlow model style generated the signal.

Allowed values:

"CONSERVATIVE"

"HULK"

"VALUE_HUNTER"

Each model style has a distinct risk profile and market behavior.

Example:

"model_style": "VALUE_HUNTER"
book_odds
Type: number
Description: The bookmaker’s offered odds at the time the signal was generated.

Example:

"book_odds": 2.40
fair_odds
Type: number
Description: OddsFlow’s estimated fair odds derived from internal probability models.

Example:

"fair_odds": 2.15
edge_pct
Type: number
Description: The estimated pricing inefficiency expressed as a percentage.

Definition:

edge = fair probability − implied market probability
Example:

"edge_pct": 4.8
confidence
Type: string
Description: A qualitative confidence tier assigned to the signal.

Allowed values:

"LOW"

"MEDIUM"

"HIGH"

Example:

"confidence": "HIGH"
last_updated_utc
Type: string (ISO 8601)
Description: Timestamp indicating when the signal was last updated (UTC).
This timestamp is always before match kickoff.

Example:

"last_updated_utc": "2026-01-21T09:00:00Z"
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

