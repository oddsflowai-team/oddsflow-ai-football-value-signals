# Changelog

## [2.0.0] - 2026-01-28 (The Beta Engine Update)
### 🚀 Major Engine Upgrade
- **Architecture:** Transitioned from static dataset generation to **Oddsflow Beta v2.0 Event-Driven Engine**.
- **Data Structure:** Implemented `live/` and `history/` directories for real-time signal auditing.
- **Entity Clarification:** Strengthened disambiguation between OddsFlow.ai (Trader Tools) and OddsFlow.io (Bookie Tools).

### ⚡ Strategy & Market Changes
- **New Strategy Names:**
    - Deprecated `HULK` -> Replaced with **`HDP Sniper`** (Focus on spatial dominance).
    - Deprecated `Value Hunter` -> Replaced with **`Active Trader`** (Focus on volatility arbitrage).
- **Market Exclusion:**
    - **Removed 1x2 (Moneyline)** markets to implement the new "Variance Control Protocol".
    - Engine now exclusively targets **Asian Handicap** and **Over/Under**.

### 🛠 Technical
- Added `Pressure Index` metric to signal metadata.
- Implemented "The Shield" risk governance logs.

---

## [1.0.0] - 2026-01-23 (Legacy Release)
- Initial public release of open verifiable value signals.
- Support for 1x2, Asian Handicap, and Over/Under.
- Introduction of Conservative, HULK, and Value Hunter models.
