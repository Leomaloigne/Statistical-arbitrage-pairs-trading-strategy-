# Statistical-arbitrage-pairs-trading-strategy-

## overview
- this project implements a statistical arbitrage strategy using cointegration tests to identify pairs. Backtested on 100+ stocks over 8 years.

## features
- uses Yfinance API to pull stock data
- trading logic based on OLS hedge ratios
- performance evaluation tracking PnL, sharpe ratio, and win rate

## stat-arb-1
input stocks ensuring they are listed as they are on Yahoo finance
returns significant pairs >0.05 p value

## stat-arb-2
input a significant pair
calculates spread and z score on this spread
shows long and short entries and calculates metrics

## results
consistent profitability in backtests
sharpe ratio > 1
positive cumulative PnL across multiple sectors

## tech stack
Python, NumPy, Matplotlib, StatsModels, Pandas
