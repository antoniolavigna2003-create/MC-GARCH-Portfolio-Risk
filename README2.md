**Monte Carlo and GARCH Portfolio Risk Analysis
Buy \& Hold vs Trend + Volatility Strategy**



*Overview*



This repository presents a quantitative risk analysis of an equity portfolio using Monte Carlo simulations and GARCH-based volatility models.
A Buy \& Hold benchmark is compared with a Trend + Volatility scaling strategy to assess differences in terminal outcomes and path-dependent risk.

The objective is risk understanding, not return forecasting.



*Data*
•Asset: S\&P 500 ETF (SPY)
•Source: Yahoo Finance
•Frequency: Daily adjusted prices
•Sample period: From 2005 onward

Returns are computed as daily simple returns.



*Strategies*

Buy \& Hold: fully invested benchmark strategy, used as a reference for market exposure.

Trend + Volatility Strategy: a dynamic allocation rule.

Combining:
•a long-term trend filter (200-day moving average),
•volatility-based exposure scaling (30-day rolling volatility).

Portfolio weights are lagged to avoid look-ahead bias and clipped to limit leverage.



*Modeling Framework*

-Monte Carlo (i.i.d.)

Returns are simulated assuming independence using:
•Normal innovations,
•Student-t innovations (fat tails, variance-standardized).

These models serve as baseline references.

-GARCH(1,1)

To capture volatility clustering, returns are generated via a GARCH(1,1) process with:
•Normal innovations,
•Student-t innovations (stress scenario).

The unconditional variance is preserved by construction. Parameters are fixed to highlight structural effects rather than estimation accuracy.



*Simulation Design*
•Horizon: 10 years
•Paths: 10,000
•Identical setup across all models and strategies

Results are evaluated on terminal wealth and path-dependent risk.



*Risk Metrics*
•Probability of ending below initial capital
•Terminal wealth percentiles (1%–99%)
•Conditional loss given a final loss
•Maximum drawdown

These metrics jointly capture distributional and path-level risk.



*Key Findings*
•Fat-tailed innovations increase downside risk and extreme outcomes.
•GARCH models produce more realistic volatility dynamics, particularly in drawdowns.
The Trend + Volatility strategy:
•reduces the probability of capital loss,
•significantly limits drawdowns,
•trades extreme upside for improved downside protection.
•results are consistent across Monte Carlo and GARCH frameworks.



*Figures*
•Figure 1: Buy \& Hold wealth paths under Monte Carlo and GARCH models.
•Figure 2: Terminal wealth distributions under a GARCH-t stress scenario.
•Figure 3: Maximum drawdown distributions highlighting path-dependent risk.



*Caveats*
•Parameters are estimated in-sample.
•Simulations are conditional on model assumptions.
•Results are not forecasts and do not constitute investment advice.



*Conclusion*

Combining Monte Carlo and GARCH simulations provides a robust framework for portfolio risk analysis.
Volatility-aware strategies can materially improve downside risk control, especially in realistic volatility regimes.



*Possible Extensions*
•Out-of-sample testing
•Parameter uncertainty
•Regime-switching volatility
•Multi-asset portfolios



***This project is intended for educational and research purposes in quantitative finance.***

