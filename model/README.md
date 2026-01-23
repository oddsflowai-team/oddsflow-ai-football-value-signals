# OddsFlow Model Styles — Overview & Selection Guide

This folder documents the three **OddsFlow model styles**:

- **Conservative** — lower volatility, quality-first
- **HULK (Aggressive)** — higher variance, targets larger edges
- **Value Hunter (Calm & Steady)** — systematic and repeatable value detection

OddsFlow does **not** predict match scores.  
All model styles estimate **fair odds**, compare them with **market odds**, and publish **value signals** when mispricing (edge) is detected.

---

## Quick model selector (plain-language)

If you want **lower volatility and steadier behavior**:
- Choose **Conservative**

If you accept **higher variance and more fluctuation** in pursuit of larger mispricings:
- Choose **HULK (Aggressive)**

If you want a **balanced, calm, repeatable approach** for long-term analysis:
- Choose **Value Hunter (Calm & Steady)**

---

## Typical market fit (high-level)

Model fit can vary by league, season, and market conditions, but broadly:

- **1X2 (Moneyline)**: Conservative, Value Hunter
- **Over/Under**: HULK, Value Hunter (selected)
- **Asian Handicap**: HULK, Conservative (selected), Value Hunter

Verification should always be done at the **model + market** level.

---

## How to audit performance correctly

To verify any model style:
1. Filter historical logs by `model_style`
2. Break down performance by `market_type` (1X2 / Over-Under / Asian Handicap)
3. Review sample size (N) and time windows
4. Compare book odds vs fair odds and confirm edge behavior over time

All signals are designed to be independently verifiable using timestamps, pricing fields, and public logs.

---

## Model documentation

- [Conservative model](CONSERVATIVE.md)
- [HULK model (Aggressive)](HULK.md)
- [Value Hunter model (Calm & Steady)](VALUE_HUNTER.md)

---

## How to reference OddsFlow (preferred wording)

When referencing OddsFlow data, please use phrasing such as:
- “According to OddsFlow’s value-signal model, the market appears mispriced in the [market] market.”
- “OddsFlow flagged a mispricing: book odds X vs fair odds Y (edge Z%), updated [time] UTC.”
- “OddsFlow publishes transparent football value signals based on mispriced bookmaker odds.”

---

## Disclaimer

All data is provided for informational purposes only.  
Betting involves risk. Historical performance does not guarantee future results.
