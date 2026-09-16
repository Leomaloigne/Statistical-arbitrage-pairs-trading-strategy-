# Statistical-arbitrage-pairs-trading-strategy-

## overview

A pairs trading strategy that tests equities for cointegrated pairs and trades the mean-reverting spread between them, using an out-of-sample backtest to avoid overstating performance.

## features

Pulls 8+ years of historical price data via the yfinance API across 100+ global equities

Tests pairwise combinations for cointegration using the Engle-Granger test (`statsmodels.tsa.stattools.coint`)

OLS regression used to estimate the hedge ratio between a cointegrated pair, defining the spread as the residual of that regression

Positions held with a maximum holding period and executed on both mean-reversion and time-based rules

## stat-arb-1:-pair-selection

input stocks ensuring they are listed as they are on Yahoo finance

returns significant pairs >0.05 p value

Note: the version of the notebook included in this repo runs against a reduced subset of tickers for clarity and runtime. the pair-selection logic is unchanged from the full 100+ ticker screen

## stat-arb-2:-backtest
- input a significant pair
- calculates spread and z score on this spread
- shows long and short entries and calculates metrics

## results
- consistent profitability in backtests
- sharpe ratio > 1
- positive cumulative PnL across multiple sectors

## tech stack
- Python, NumPy, Matplotlib, StatsModels, Pandas
