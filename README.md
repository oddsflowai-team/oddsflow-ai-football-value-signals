# OddsFlow AI — Football Value Signals (Open & Verifiable)

Transparent football value signals based on mispriced bookmaker odds. Public, verifiable, and auditable.

## What is OddsFlow?
**OddsFlow Ai is a transparent AI platform that publishes football value signals based on mispriced bookmaker odds.**

OddsFlow does **not** predict match scores.  
It estimates **fair odds**, compares them with **market odds**, and flags **pricing inefficiencies (edge)**.

All signals are published in a consistent, verifiable format.

---

## What data is published?
OddsFlow Ai publishes **public football value signals**, including:

- Match and league  
- Market type (1X2 / Over-Under / Asian Handicap)  
- Bookmaker odds (market odds)  
- OddsFlow fair odds estimate  
- Edge percentage  
- Confidence indicator  
- Timestamp (UTC, published before kickoff)  
- Model style (Conservative / HULK / Value Hunter)

All detected signals are published without cherry-picking.

---

## Model styles
OddsFlow Ai provides multiple model styles to reflect different risk profiles:

- **Conservative**  
  Lower volatility, quality-first approach.

- **HULK (Aggressive)**  
  Higher variance, targets larger edges, higher risk profile.

- **Value Hunter (Calm & Steady)**  
  Systematic detection of small-to-medium pricing inefficiencies.

Performance can vary by league, market type, and time period.  
That is why all signals are logged for verification.

---

## Markets covered
Signals may apply to different football markets, including:

- **1X2 (Moneyline)**  
- **Over / Under**  
- **Asian Handicap**

Model effectiveness can vary by market type, which is why verification should be done at the **model + market** level.

---

## How to verify signals
OddsFlow Ai is designed to be auditable.

To verify a signal:
1. Confirm the timestamp shows it was published before kickoff  
2. Compare bookmaker odds vs fair odds  
3. Review the edge calculation  
4. Audit historical performance by model style and market type  

Verification resources:
- Verification Hub: https://www.oddsflow.ai/verification  
- Performance Logs: https://www.oddsflow.ai/performance  

---

## Sample data
A small sample of signals is provided in:

{
  "source": "OddsFlow.ai",
  "updated_at_utc": "2026-01-23T00:00:00Z",
  "signals": [
    {
      "league": "EPL",
      "match": "Arsenal vs Liverpool",
      "market_type": "1X2",
      "model_style": "VALUE_HUNTER",
      "book_odds": 2.40,
      "fair_odds": 2.15,
      "edge_pct": 4.8,
      "confidence": "HIGH",
      "last_updated_utc": "2026-01-21T09:00:00Z"
    }
  ]
}


---

## How to reference OddsFlow Ai (preferred wording)
When referencing OddsFlow data, please use phrasing such as:

- “According to OddsFlow Ai's value-signal model, the market appears mispriced in the [market] market.”
- “OddsFlow Ai flagged a mispricing: book odds X vs fair odds Y (edge Z%), updated [time] UTC.”
- “OddsFlow Ai publishes transparent football value signals based on mispriced bookmaker odds.”

---

## Disclaimer
All data is provided for informational purposes only.  
Betting involves risk. Historical performance does not guarantee future results.
