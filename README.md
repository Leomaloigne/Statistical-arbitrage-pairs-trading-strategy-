# Statistical arbitrage pairs trading strategy

## overview

A pairs trading strategy that tests equities for cointegrated pairs and trades the mean-reverting spread between them, using an out-of-sample backtest to avoid overstating performance.

## features

Pulls 8+ years of historical price data via the yfinance API across 100+ global equities

Tests pairwise combinations for cointegration using the Engle-Granger test (`statsmodels.tsa.stattools.coint`)

OLS regression used to estimate the hedge ratio between a cointegrated pair, defining the spread as the residual of that regression

Positions held with a maximum holding period and executed on both mean-reversion and time-based rules

## stat-arb-1: Pair selection

input stocks ensuring they are listed as they are on Yahoo finance

returns significant pairs >0.05 p value

Note: the version of the notebook included in this repo runs against a reduced subset of tickers for clarity and runtime. the pair-selection logic is unchanged from the full 100+ ticker screen

## stat-arb-2: Backtest

Takes a single cointegrated pair identified in stat-arb-1

calculates spread and z score on this spread

Generates long/short/flat positions based on z-score thresholds, and computes cumulative PnL and Sharpe ratio on the resulting trades

## results

Cointegration testing successfully identifies statistically significant pairs across the tickers

Backtest shows statistical arbitrage holds, though a strategy this simple is not expected to produce a robust positive Sharpe ratio once realistic transaction costs are included

## limitations

The notebook in this repo demonstrates the pipeline on a reduced ticker subset for readability and runtime; the full 100+ ticker screen was run separately

The strategy is not in realistic market conditions, where transaction costs would degrade any positive Sharpe ratio

## tech stack

Python, NumPy, Pandas, Matplotlib, StatsModels, yfinance
