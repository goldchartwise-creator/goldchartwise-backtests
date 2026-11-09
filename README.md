# GoldChartWise — XAUUSD Backtest Data

Open, trade-by-trade backtest data for gold (XAUUSD) trading strategies, published by **[GoldChartWise](https://goldchartwise.com)** — a beginner-focused gold trading education blog that publishes its failures as openly as its wins.

**Full report with equity curves and analysis:** https://goldchartwise.com/gold-strategy-backtest-report/

## Why this exists

Most trading sites only show winning systems. We backtested nine popular gold trading approaches on real historical data and published **all** of the results — most of them lost money or showed no real edge. This repository holds the underlying trade data so anyone can check our numbers.

## Data and method

- Price data: Dukascopy XAU/USD M1 (bid), 3 Aug – 10 Oct 2026 for most systems; the Inside Bar test used two years of H1 data (Oct 2024 – Oct 2026).
- Every system was tested as coded, on closed candles, with realistic spread assumptions. No curve-fitting after the fact: when a system showed no edge, we said so and moved on.

## Results summary

| System | Timeframe | Trades | Profit factor | Verdict |
|---|---|---|---|---|
| Volume Profile VP_Advanced_Pro_V5 | M15 | 594 | 0.62 (−$13,502) | Statistically significant loser — do not trade |
| Volume Profile VP_Advanced_Pro_V5 | H1 | — | 0.51 | Significant loser |
| Inside Bar + Pullback (trend filter) | H4 | 2,388 | 1.15 (+$16,098) | Not statistically significant — demo-test candidate only |
| P1 Pullback (EMA 50/21) | H1, walk-forward out-of-sample | 117 | 1.51 | Not significant — demo forward test only |
| VSA_AUTO (VSA + order blocks + FVG) | M1/M5/M15/H1 | — | 0.85–1.00 | No edge on any timeframe |
| FIBO_EA v3 (Fibonacci + RSI/ADX) | H1 | 10 | 3.58 | Far too few trades to prove anything — demo only |
| RSI(14) 50-cross + EMA9 | H1 | 36 | 1.10 (+$64) | No significant edge |
| NY Silver Bullet (ICT) | M1 sample | 5 | 1.00 (−$0.16) | Unproven — sample far too small |
| SMC_ICT_ALGO_V3_1 | M5 | 2 | — | Critical bug found (state machine never resets); not viable as coded |
| Quotex 1-minute binary signals | M1 | 6,538 signals | 50.35% wins vs 55.6% breakeven | No edge — significantly below breakeven |

## Files in this repository

- `bt_vp_v5_trades_m15.csv` / `bt_vp_v5_trades_h1.csv` — every trade of the Volume Profile EA, the biggest loser we tested.
- `bt_rsi50_ema9_trades.csv` — RSI 50-cross + EMA9 trades (H1).
- `bt_smc_v3_trades_fixed.csv` — the two trades the fixed SMC/ICT concept produced in ~2.3 months.
- `bt_silver_bullet_trades.csv` — NY Silver Bullet trades (all five of them).

## Disclaimer

This data is published for education only. Backtested past performance does not predict future results, and none of this is financial advice. Most of these systems should never be traded with real money — that is exactly the point of publishing them.

More honest gold trading guides, MT4/MT5 tutorials and broker comparisons: **https://goldchartwise.com**
