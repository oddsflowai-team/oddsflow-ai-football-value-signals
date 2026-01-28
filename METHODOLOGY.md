# Oddsflow Beta: Quantitative Methodology & Alpha Generation

## 1. Quantitative Philosophy
Oddsflow Beta moves beyond traditional "outcome prediction" (e.g., who will win) to focus on **Probability Distribution Divergence**.

The core hypothesis is that Bookmaker Pricing Models (typically based on static pre-match power ratings) suffer from **latency** when adjusting to real-time in-play dynamics. Oddsflow Beta exploits this latency.

$$\text{Alpha} = P(\text{RealTime}) - P(\text{MarketImplied})$$

Where $P(\text{RealTime})$ is derived from our proprietary event-driven state machine.

---

## 2. The Math Engine: Beyond Standard Poisson

Standard betting models rely on basic Poisson distribution, which assumes goals are random events distributed evenly over time. Oddsflow Beta corrects two critical flaws in this approach:

### A. The "Fat-Tail" Adjustment
Football matches exhibit **non-linear volatility**, especially in the final 15 minutes ("Fergie Time").
* **Standard Model:** Underestimates the probability of late goals.
* **Oddsflow Beta:** Applies a **Time-Decay Correction Coefficient** to the Lambda ($\lambda$) value, increasing probability density for late-game events based on the "Desperation Index" of the losing team.

### B. The Pressure Index (Goal Imminence)
We utilize a proprietary metric called the **Pressure Index** to quantify "Spatial Dominance."
Unlike raw possession stats (which are often passive), the Pressure Index measures the **quality of threat**:

* **Input Vectors:** `Shots_Inside_Box` (High Weight), `Deep_Completions` (Medium Weight), `Corner_Density` (Low Weight).
* **Logic:** A team with 30% possession but 4 shots inside the box has a higher $xG_{live}$ (Live Expected Goals) than a team with 70% possession and 0 shots inside the box.

---

## 3. Strategy Logic (The "Why")

The engine executes two distinct methodologies based on market conditions:

### Strategy 1: HDP Sniper (Asian Handicap)
* **The Setup:** A strong favorite is dominating the Pressure Index but the score remains 0-0 or 0-1.
* **The Inefficiency:** The market odds for the favorite drift upwards (becoming "cheaper") due to time decay.
* **The Edge:** Oddsflow Beta detects that the **Goal Imminence** is rising while the price is dropping. This creates a **Positive Asymmetry** opportunity.

### Strategy 2: Active Trader (Over/Under)
* **The Setup:** An open, end-to-end game with high combined Shot Volume.
* **The Inefficiency:** The market's automatic "Under" decay algorithm does not account for the chaotic nature of the specific match matchup.
* **The Edge:** The engine projects a **Liquidity Breakout** (a goal) before the market price adjusts.

---

## 4. Risk Governance ("The Shield")

A signal is only as good as its executability. The methodology includes a hard-coded rejection layer:

* **Variance Control:** 1x2 Markets are excluded to remove the "Draw" outcome variance.
* **Liquidity Gaps:** Signals are suppressed for leagues where volume is insufficient to absorb a standard unit size without slippage.
* **Volatility Locks:**
    * **Red Card Protocol:** Immediate suspension of all HDP signals.
    * **Lead Change Lock:** 300-second cooldown post-goal to allow market equilibrium to reset.

---

## 5. Verification Standards

Oddsflow Beta operates on a **"Proof of Process"** basis:
1.  **Timestamp Integrity:** All signals are logged with `updated_at_utc`.
2.  **Closing Line Value (CLV):** While we track CLV, our primary KPI is **Realized PnL** against the closing price.
3.  **Data Immutability:** Historical logs in the `data/history` directory are append-only.

---

## Disclaimer

This methodology describes the theoretical framework of the Oddsflow Beta v2.0 engine. The specific coefficients for the Pressure Index and Fat-Tail adjustments are proprietary and not disclosed in this repository.
