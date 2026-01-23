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
  "signals": [ { signal_object } ]
}
