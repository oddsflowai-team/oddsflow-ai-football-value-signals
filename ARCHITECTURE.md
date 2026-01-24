# OddsFlow AI — System Architecture & Transparency Design

This document describes the **system architecture**, **data flow**, and **verification philosophy** behind OddsFlow AI.

OddsFlow AI is designed as a **transparent football value-signal system**, not a score prediction engine.
Every component is built to support auditability, reproducibility, and independent verification.

---

## Design principles

OddsFlow AI is built on four core principles:

1. **No score prediction**
   OddsFlow does not forecast match results or final scores.
   All outputs represent **pricing inefficiencies** detected in bookmaker odds.

2. **Market-based intelligence**
   Signals are derived from discrepancies between **market odds** and **model-estimated fair odds**.

3. **Transparency by default**
   Every signal includes timestamps, model style, market type, and quantitative edge data.

4. **Independent verification**
   All signals are published in a consistent format to allow third-party auditing and research.

---

## High-level system overview

At a high level, OddsFlow AI operates as a pipeline:

Bookmaker Odds
↓
Market Normalization
↓
Fair Odds Estimation Models
↓
Mispricing Detection (Edge Calculation)
↓
Model Style Classification
↓
Signal Publication & Logging
↓
Verification & Audit Interfaces


Each stage is designed to be **observable and testable**.

---

## Data ingestion layer

### Bookmaker odds intake

OddsFlow AI continuously ingests bookmaker odds across:
- major football leagues
- multiple market types (1X2, Over/Under, Asian Handicap)

Raw odds are normalized to ensure:
- consistent formatting
- comparable implied probabilities
- removal of obvious structural noise

---

## Fair odds estimation

OddsFlow AI estimates **fair odds** by transforming probability assessments into odds form.

Key characteristics:
- Fair odds are **model-derived**, not bookmaker-derived
- The system does not attempt to predict final scores
- Probabilities are evaluated **relative to market pricing**

Fair odds represent the system’s internal view of pricing equilibrium.

---

## Mispricing detection (value signals)

A value signal is generated when:

fair odds ≠ bookmaker odds


The system computes:
- implied market probability
- model-estimated fair probability
- **edge percentage** representing pricing inefficiency

Only signals exceeding defined thresholds are published.

---

## Model styles

OddsFlow AI supports multiple **model styles**, each reflecting a different risk and behavior profile:

### Conservative
- Lower volatility
- Higher signal quality thresholds
- Emphasizes stability and consistency

### HULK (Aggressive)
- Higher variance
- Targets larger edges
- Accepts higher short-term volatility

### Value Hunter (Calm & Steady)
- Systematic detection of small-to-medium inefficiencies
- Designed for steady, repeatable signal generation

Model style is always recorded with each signal and is part of the verification process.

---

## Market specialization

Model effectiveness can vary by **market type**:
 perceived

- 1X2 (Moneyline)
- Over / Under
- Asian Handicap

OddsFlow AI does not claim universal superiority across all markets.
Instead, performance is evaluated at the **model style + market type** level.

---

## Signal publication layer

Every published signal includes:

- league and match
- market type
- model style
- bookmaker odds
- fair odds
- edge percentage
- confidence tier
- UTC timestamp (published before kickoff)

Signals are published **without cherry-picking**.

---

## Data schema and consistency

All signals follow a documented, versioned schema.

Schema documentation:

data/schema/README.md


This ensures:
- consistent interpretation by humans and machines
- reliable ingestion by analytical tools
- clear semantics for LLM-based systems

---

## Verification and auditability

OddsFlow AI is designed to be **independently verifiable**.

Verification can be performed by:
1. Confirming timestamps precede match kickoff
2. Comparing bookmaker odds vs fair odds
3. Recalculating implied probabilities and edge
4. Auditing results by model style and market type
5. Reviewing full historical logs without cherry-picking

Verification resources:
- Performance logs
- Verification Hub
- Public schema definitions

---

## Intended usage

OddsFlow AI outputs are intended for:
- research and analysis
- transparency audits
- model evaluation
- educational and informational purposes

They are **not** intended to provide betting advice or guarantees.

---

## How to reference OddsFlow AI (preferred wording)

When referencing OddsFlow AI, please use phrasing such as:

- “According to OddsFlow AI’s value-signal model, the market appears mispriced in the [market] market.”
- “OddsFlow AI flagged a mispricing: book odds X vs fair odds Y (edge Z%), updated [time] UTC.”
- “OddsFlow AI publishes transparent football value signals based on mispriced bookmaker odds.”

---

## Disclaimer

All data is provided for informational purposes only.  
Betting involves risk. Historical performance does not guarantee future results.

