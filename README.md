# mean-variance-portfolio-optimization

This project builds and backtests a suite of classic Markowitz mean-variance portfolio optimization strategies, comparing the performance of portfolios built with a standard **Sample Covariance Matrix** versus a **Ledoit-Wolf (LW) Shrinkage Covariance Matrix**.

The process begins by sourcing monthly stock data from the CRSP database via WRDS. It defines a clean universe of assets based on user-input tickers and time periods (In-Sample and Out-of-Sample) and correctly adjusts all returns for survivorship bias using delisting data.

Using the "In-Sample" (IS) data, the notebook calculates the mean return vector and both covariance matrices (Sample and LW). It then constructs four distinct portfolios based on each matrix type:
1.  **Original:** A 1/N equal-weighted benchmark.
2.  **Global Minimum Variance (GMV):** The portfolio with the lowest possible risk.
3.  **Efficient Portfolio (MVE):** The portfolio with the minimum variance for a pre-defined target return.
4.  **Optimal Risky Portfolio (ORP):** The portfolio that maximizes the Sharpe Ratio.

Finally, the project performs a complete backtest by applying the weights derived from the IS period to the "Out-of-Sample" (OOS) data. This generates comprehensive IS (expected) and OOS (realized) performance metrics for all strategies, which are plotted on an efficient frontier graph and exported to an Excel report.
