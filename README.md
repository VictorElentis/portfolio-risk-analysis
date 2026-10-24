# README for repo: portfolio-risk-analysis

# Portfolio Risk Analysis: Volatility, VaR and Drawdown

How risky is a stock portfolio, how much could it lose in a bad month, and how much capital should be set aside? This project measures portfolio risk several ways and tests whether the measures hold up in a crisis.

## Data
Monthly prices for AAPL, AMZN, IBM and MSFT from January 2000 to March 2010 (123 months), from the `vega-datasets` collection. The period covers the dot-com bust and the 2008 financial crisis.

## Approach
- Calculated returns, volatility and correlations, and measured how much diversification reduced risk
- Estimated Value at Risk (historical and parametric) and Expected Shortfall at 95% and 99%
- Backtested 95% VaR on rolling 36-month windows
- Measured maximum drawdown and stress-tested both crashes
- Simulated 10,000 one-year outcomes with a Monte Carlo model
- Used an optimizer to find minimum-variance weights and compared them with equal weights

## Key findings
- Diversification cut annual volatility from 43.5% (average of the stocks) to 33.5%, but the stocks were highly correlated (0.39 to 0.57)
- 95% monthly VaR was 15.8% (about $15,800 on $100,000); Expected Shortfall was 18.3%
- VaR was breached in 7 of 86 months (8.1% vs 5% expected), and six breaches came in 2008
- Maximum drawdown was -64.3%; a bad year (5th percentile) lost about $35,400 in simulation
- The minimum-variance portfolio had lower risk but return per unit of risk fell from 0.51 to 0.19

## How to run
Open `portfolio_risk_analysis.ipynb` in Google Colab and select Runtime, then Run all. The data loads from GitHub, so nothing needs downloading.

## Limitations and next steps
Survivorship bias, monthly data, no dividends or costs, and a normal assumption in two methods. Next: daily data, GARCH volatility, other asset classes, and a Kupiec backtest.
