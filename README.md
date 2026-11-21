# Live_Signal

## Live Signal Tracking Methodology

- Model updates: Quarterly retraining; historical out-of-sample signals remain unchanged.
- Rebalancing: Daily, using VWAP of the first half hour as the assumed execution price.
- Exclusions: ST stocks, suspended stocks, stocks newly listed in the current quarter, and stocks with fewer than 40 trading days in the past 60 trading days.
- Transaction costs: Evaluated at 5 and 15 bps.
- Turnover: Reported on a one-way basis.
- Optimizer: Constrains active exposures to eight **Barra style factors to ±0.3** relative to the benchmark and penalizes risk using **stock-specific risk** and **Barra style-factor covariance**. Enforces full investment, long-only positions, a 0.5% per-stock weight cap, a 15% one-way turnover limit, and per-stock liquidity limits.


## Signal Performance

Sample period: January 2, 2020–September 30, 2026.  
OOS period: April 1, 2025–September 30, 2026.  
Annualization assumes 250 trading days.

### Strategy, Benchmark and Excess Performance

![Strategy, benchmark and excess performance](01_strategy_benchmark_excess.png)

| Metric | In-sample | OOS |
|---|---:|---:|
| Trading observations | 1,269 | 367 |
| Annualized arithmetic excess | 24.39% | 20.81% |
| Information ratio | 4.12 | 3.31 |
| Maximum additive excess drawdown | 5.36 pp | 6.93 pp |
| Positive excess months | 90.48% | 88.89% |

Daily strategy returns are calculated as daily excess plus benchmark
returns. Strategy and benchmark curves are compounded. Relative cumulative
excess equals strategy wealth divided by benchmark wealth, minus one.
Additive excess drawdown is measured in percentage points (pp).

### Out-of-Sample Performance

![OOS performance](02_oos_performance.png)

The OOS segment generates 31.17 percentage points of cumulative additive
excess across 367 observations. Annualized arithmetic excess is 20.81%,
with an information ratio of 3.31.

Compared with in-sample results, annualized excess decreases by 3.58
percentage points, while tracking error increases from 5.92% to 6.28%.

## Return Decomposition

This decomposition uses constructed excess returns and actual daily Barra factor returns. It is not measured live holdings-based attribution. All 20 fitted active style exposures are bounded at ±0.3.

The calibration uses 245 trading days per year and the source company portfolio’s OPEN execution and saved transaction costs, which differ from the methodology above.

### Cumulative Return Attribution

| Cumulative contribution (pp) | IS | OOS |
|---|---:|---:|
| 20 style factors | +37.29 | +12.07 |
| Industry / country | +5.43 | −0.74 |
| Model residual | +97.73 | +25.11 |
| Costs | −14.11 | −5.27 |
| **Net excess return** | **+126.33** | **+31.17** |

The residual row groups model, execution-timing and benchmark-difference components. Totals are calculated before rounding.

### Overall Return Decomposition

![Return decomposition](07_return_decomposition.png)

Curves show cumulative daily contributions in percentage points and restart at the beginning of each period. The residual curve uses the same definition as the table. Industry/country contributions and costs are reported separately.

### Contributions from 20 Barra Style Factors

![20 Barra style factor contributions](08_style_factor_contributions.png)

Each daily factor contribution equals its fitted active exposure multiplied by the actual factor return. Contributions sum to **+37.29 pp IS** and **+12.07 pp OOS**.

Exposures are fitted using realized returns and period totals. The exposure bounds alone do not establish portfolio feasibility or tradability.
### Monthly Consistency

![Monthly excess returns](03_monthly_consistency.png)

Excess returns are positive in 16 of 18 OOS months. The strongest OOS
month is May 2025 (+4.28 pp); the weakest is June 2026 (-5.36 pp).
January–September 2026 contributes 12.46 pp of additive excess.

### Rolling Performance and Drawdown

![Rolling information ratio and tracking error](04_rolling_risk.png)

The maximum OOS additive excess drawdown is 6.93 pp, from the
June 1, 2026 peak to the June 30, 2026 trough. The previous peak
is recovered on September 4, 2026.

At September 30, 2026, the trailing 63-day information ratio is 3.65,
compared with 3.31 for the full OOS period. Rolling windows use
63 observations and may span the IS/OOS boundary.

Illustrative supplied-series analysis. OOS denotes the specified date
segment, not independent live validation. The supplied return file does
not identify a transaction-cost scenario.

## Part Two: Incremental Contribution

Sample period: January 2, 2020–September 30, 2026.  
OOS period: April 1, 2025–September 30, 2026.

### Improvement over the Company Baseline

![Combined signal versus company baseline](05_combination_improvement.png)

| OOS metric | Company baseline | Combined signal | Change |
|---|---:|---:|---:|
| Annualized excess return | 21.42% | 24.38% | +2.96 pp |
| Information ratio | 3.74 | 4.52 | +0.78 |
| Maximum additive excess drawdown | 4.93 pp | 5.26 pp | +0.33 pp |
| Cumulative additive excess | 33.59 pp | 36.55 pp | +2.96 pp |

The combined signal delivers higher excess return and better
risk-adjusted performance than the company baseline. Tracking error
decreases, although maximum additive excess drawdown widens slightly.

Changes are calculated before rounding. Annualization assumes
250 trading days; pp denotes percentage points.


![Daily excess-return correlation](06_signal_correlation.png)

| Metric | In-sample | OOS | Full sample |
|---|---:|---:|---:|
| Trading observations | 1,269 | 367 | 1,636 |
| Daily excess-return correlation | 0.519 | 0.580 | 0.534 |
