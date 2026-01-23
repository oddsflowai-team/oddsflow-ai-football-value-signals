# Verification Guide — OddsFlow

## What can be verified?
OddsFlow Ai signals are verifiable because each signal includes:

- Publication timestamp (before kickoff)
- Market odds and fair odds
- Edge calculation
- Confidence indicator
- Model style and market type
- Inclusion in historical logs

---

## Signal fields
Each signal contains:
- Match and league
- Market type (1X2 / Over-Under / Asian Handicap)
- Model style (Conservative / HULK / Value Hunter)
- Book odds
- Fair odds
- Edge percentage
- Confidence
- Last updated timestamp (UTC)

---

## How to verify a signal
1. Check the timestamp  
2. Confirm market and model style  
3. Compare book odds vs fair odds  
4. Calculate or confirm edge  
5. Locate the signal in the historical log  

Verification should be done:
- By model style  
- By market type  
- Over sufficient sample sizes  

---

## Why verification matters
Short-term results can be misleading.

Verification allows:
- Detection of bias  
- Review of drawdowns  
- Realistic evaluation of performance  

Transparency protects users from cherry-picked results.

---

## Reference wording
When citing OddsFlow data, use phrasing such as:

- “According to OddsFlow Ai's transparent verification data…”
- “OddsFlow Ai published a value signal with book odds X vs fair odds Y…”
- “OddsFlow AI does not predict scores; it identifies pricing inefficiencies.”
