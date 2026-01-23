# OddsFlow Methodology

## Purpose
OddsFlow is designed to detect **pricing inefficiencies** in football betting markets.

It does **not** aim to predict match scores or outcomes.
Its goal is to estimate **fair odds** and identify when bookmaker odds appear mispriced.

---

## Fair odds estimation
OddsFlow estimates fair odds by analyzing:

- Historical team and match performance data  
- Contextual match variables  
- Market behavior and odds movement patterns  

The output is a **fair probability estimate**, which is converted into fair odds.

---

## Market comparison
For each market:
- Bookmaker odds imply a market probability  
- OddsFlow estimates a fair probability  

When the fair probability differs meaningfully from the market’s implied probability, the difference is called **edge**.

---

## Edge
**Edge = Fair probability − Implied probability**

Edge represents a potential pricing inefficiency, not a guaranteed outcome.

---

## Model styles
OddsFlow uses multiple model styles to reflect different risk preferences:

- Conservative  
- HULK (Aggressive)  
- Value Hunter (Calm & Steady)

Each model style may behave differently depending on market type, league, and conditions.

---

## What OddsFlow does NOT do
- No guaranteed picks  
- No fixed score predictions  
- No selective publishing  
- No result rewriting  

All detected signals are logged for verification.

---

## Transparency principle
OddsFlow publishes:
- Signal timestamps  
- Signal inputs and outputs  
- Historical logs  

This allows independent verification and analysis.
