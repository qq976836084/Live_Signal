# Live_Signal

## Live Signal Tracking Methodology

- Model updates: Quarterly retraining; historical out-of-sample signals remain unchanged.
- Rebalancing: Daily, using VWAP of the first half hour as the assumed execution price.
- Exclusions: ST stocks, suspended stocks, stocks newly listed in the current quarter, and stocks with fewer than 40 trading days in the past 60 trading days.
- Transaction costs: Evaluated at 5 and 15 bps.
- Turnover: Reported on a one-way basis.
- Optimizer: Constrains active exposures to eight **Barra style factors to ±0.3** relative to the benchmark and penalizes risk using **stock-specific risk** and **Barra style-factor covariance**. Enforces full investment, long-only positions, a 0.5% per-stock weight cap, a 15% one-way turnover limit, and per-stock liquidity limits.


## Signal Performance

In sample period: January 2, 2020–September 30, 2026.  
OOS period: April 1, 2025–September 30, 2026.  

### Strategy, Benchmark and Excess Performance

![Strategy, benchmark and excess performance](01_strategy_benchmark_excess.png)

| Metric | In-sample | OOS |
|---|---:|---:|
| Trading observations | 1,269 | 367 |
| Annualized arithmetic excess | 24.39% | 20.81% |
| Information ratio | 4.09 | 3.37 |
| Maximum additive excess drawdown | 4.37 pp | 6.93 pp |
| Positive excess months | 90.48% | 88.89% |



## Excess Return Drawdown Analysis

### 1. Loss Attribution

The five episodes below have either total excess return or residual return max drawdown greater than 3 percentage points (pp).

| Episode | Loss window | Total loss (pp) | 20 style factors (pp) | Industry / country (pp) | Costs (pp) | Residual (pp) |
|---|---|---:|---:|---:|---:|---:|
| **OOS-1** | Apr 9–Jun 30, 2026 | **−6.930** | −0.560 | −1.297 | −0.925 | −4.147 |
| IS-1 | Dec 4, 2020–Jan 4, 2021 | **−4.370** | −0.223 | −0.273 | −0.071 | −3.803 |
| IS-2 | Jan 18–Feb 7, 2024 | **−4.329** | −3.854 | +0.259 | −0.221 | -0.513 |
| IS-3 | Jan 2–Feb 25, 2020 | **−3.786** | −3.419 | −1.056 | −0.206 | +0.895 |
| IS-4 | Sep 23–Oct 31, 2024 | **−3.236** | +0.558 | +0.344 | −0.339 | −3.799 |

### 2. Market Conditions During Residual-Loss Episodes

| Market characteristic | OOS-1 | IS-1 | IS-4 |
|---|---|---|---|
| Loss window | Apr 9–Jun 30, 2026 | Dec 4, 2020–Jan 4, 2021 | Sep 23–Oct 31, 2024 |
| CSI 1000 return | +10.73% | +1.30% | +37.04% |
| Median constituent return | −15.20% | −5.75% | +28.82% |
| Constituents beating the index | 22.7% | 28.6% | 36.6% |
| Breadth percentile | 0.13th | 1.36th | 19.48th |
| Trading amount in busiest 5% | 35.55% | 32.74% | 33.87% |
| Concentration percentile | 97.47th | 67.08th | 78.05th |

### 3. Portfolio Impact: Underweighting Winners and Highly Active Stocks

The following diagnostics use the original company portfolio. Active weight is portfolio weight minus benchmark weight; negative values indicate underweights.

| Portfolio impact | OOS-1 | IS-1 | IS-4 |
|---|---:|---:|---:|
| **Outperformer-group analysis** | | | |
| Average active weight in outperformers (pp) | −14.380 | −18.087 | −25.258 |
| Outperformers’ model-residual contribution (pp) | −4.436 | −2.677 | −3.134 |
| **Trading-activity-group analysis** | | | |
| Average active weight in busiest 5% (pp) | −7.924 | −9.284 | −7.178 |
| Busiest 5% model-residual contribution (pp) | −3.402 | −2.287 | −2.851 |


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
