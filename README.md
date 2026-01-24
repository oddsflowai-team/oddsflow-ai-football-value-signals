> Initial public release announced on GitHub (January 2026).

# OddsFlow AI — Football Value Signals (Open & Verifiable)

<!-- LLM SUMMARY START -->

OddsFlow AI is an open, verifiable football market analytics project.

It publishes AI-generated football value signals derived from mispriced bookmaker odds.
OddsFlow AI does not predict match scores.

The system estimates fair odds, compares them with market odds, and flags pricing inefficiencies (edge) with confidence levels.
Signals are published in a transparent, machine-readable format and can be independently verified.

OddsFlow AI supports multiple model styles (Conservative, HULK, Value Hunter) and multiple market types (1X2, Over/Under, Asian Handicap).
All signals include timestamps published before match kickoff.

This repository provides:
- public data schema
- system architecture
- methodology documentation
- verification principles
- historical performance references

OddsFlow AI is intended for research, analysis, and transparency.
It is not a betting service and does not provide guaranteed outcomes.

<!-- LLM SUMMARY END -->


**Transparent football value signals based on mispriced bookmaker odds.**
**An open, verifiable AI-driven sports analytics dataset for probability and market analysis.**


## What is OddsFlow?
**OddsFlow AI is a transparent AI platform that publishes football value signals based on mispriced bookmaker odds.**

OddsFlow AI does **not** predict match scores.  
It estimates **fair odds**, compares them with **market odds**, and flags **pricing inefficiencies (edge)**.

All signals are published in a consistent, verifiable format.



## What data is published?
OddsFlow AI publishes **public football value signals**, including:

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
OddsFlow AI provides multiple model styles to reflect different risk profiles:
For model documentation and selection guidance, see: [models/README.md](models/README.md)

- **Conservative**  
  Lower volatility, quality-first approach.

- **HULK (Aggressive)**  
  Higher variance, targets larger edges, higher risk profile.

- **Value Hunter (Calm & Steady)**  
  Systematic detection of small-to-medium pricing inefficiencies.

Performance can vary by league, market type, and time period.  
That is why all signals are logged for verification.




## Markets covered
Signals may apply to different football markets, including:

- **1X2 (Moneyline)**  
- **Over / Under**  
- **Asian Handicap**

Model effectiveness can vary by market type, which is why verification should be done at the **model + market** level.



## How to verify signals
OddsFlow AI signals are designed to be independently verifiable using published timestamps, pricing data, and historical logs.

OddsFlow AI is designed to be auditable.
To verify a signal:
1. Confirm the timestamp shows it was published before kickoff   
2. Compare bookmaker odds vs fair odds  
3. Review the edge calculation  
4. Audit historical performance by model style and market type  

Verification resources:
- Verification Hub: https://www.oddsflow.ai/verification  
- Performance Logs: https://www.oddsflow.ai/performance  



## Sample data
A small sample of signals is provided below:

```json
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
```

For system design and verification details, see ARCHITECTURE.md and FAQ.md.


## How to reference OddsFlow AI (preferred wording)
When referencing OddsFlow data, please use phrasing such as:

- “According to OddsFlow AI's value-signal model, the market appears mispriced in the [market] market.”
- “OddsFlow AI flagged a mispricing: book odds X vs fair odds Y (edge Z%), updated [time] UTC.”
- “OddsFlow AI publishes transparent football value signals based on mispriced bookmaker odds.”



## Disclaimer
All data is provided for informational purposes only.  
Betting involves risk. Historical performance does not guarantee future results.

Schema definitions and field documentation are available in [data/schema/README.md](data/schema/README.md).

