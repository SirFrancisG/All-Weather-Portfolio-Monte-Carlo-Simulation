# All-Weather-Portfolio-Monte-Carlo-Simulation
Monte Carlo simulation for an All Weather–style portfolio (Normal &amp; Student-t), using historical data from yfinance. Educational only.
# All Weather Monte Carlo Simulator (Educational)

Monte Carlo simulation of an “All Weather–style” portfolio using historical market data to estimate a distribution of possible future outcomes (portfolio paths, final value distribution, return distribution, and threshold probabilities).

> **Important note:** “All Weather” is widely discussed online, but this repository implements a **commonly cited approximation** for educational purposes. It is **not** an official or authoritative representation of any person’s or firm’s portfolio.

---

## Strong Disclaimer (Read This)
THIS REPOSITORY IS PROVIDED FOR EDUCATIONAL AND INFORMATIONAL PURPOSES ONLY.

- **NOT FINANCIAL ADVICE.** Nothing here is investment advice, research, a recommendation, or an offer to buy/sell securities.
- **HYPOTHETICAL RESULTS.** Simulations are based on historical estimates and simplifying assumptions. Outputs are hypothetical and may be materially wrong.
- **NO WARRANTY.** The software is provided “AS IS”, without any warranty of any kind. You use it at your own risk.
- **DATA QUALITY.** Price data is fetched via `yfinance` (Yahoo Finance). Data may be incomplete, delayed, adjusted, or erroneous.
- **NO AFFILIATION.** This project is not affiliated with, endorsed by, or sponsored by any person, Bridgewater, Ray Dalio, Yahoo, or any data provider.
- **LIMITATION OF LIABILITY.** The author are not liable for any losses or damages resulting from the use of this code or its outputs.

If you use this code, you accept full responsibility for any decisions you make.

---

## Portfolio (commonly cited approximation)
This implementation uses a typical ETF proxy version of an All Weather–style allocation:

- 30% US equities: `VTI`
- 40% Long-term US Treasuries (20+): `TLT`
- 15% Intermediate US Treasuries (7–10): `IEF`
- 7.5% Gold: `GLD`
- 7.5% Broad commodities: `DBC`

Example snippet:
```python
tickers = ["VTI", "TLT", "IEF", "GLD", "DBC"]
weights = np.array([0.30, 0.40, 0.15, 0.075, 0.075])

weights = weights / weights.sum()
assert np.isclose(weights.sum(), 1.0)
