# SPX Collar Simulator

## Clone and run

```bash
git clone https://github.com/pruedi123/spx-collar-simulator.git
cd spx-collar-simulator
open index.html
```

The app is a self-contained HTML file. It has no build step, package installation, server, or internet requirement. On Windows or Linux, open `index.html` directly in a modern browser after cloning.

## Project documents

- [Public simulator comparison (PDF)](docs/public-simulator-comparison.pdf) — a candid review of where public alternatives are stronger and where this project is better suited to portfolio-level education.

## What it does

The simulator illustrates a one-year European-style SPX collar for either a closely tracking S&P 500 portfolio or a different equity portfolio with an estimated beta and tracking error:

- Long put at 90% of the starting index level
- Short call at 110% of the starting index level
- Whole-contract sizing using the entered SPX level and the $100 contract multiplier
- Adjustable target hedge coverage and beta-adjusted notional
- Choice of PM-settled SPXW or AM-settled traditional SPX convention
- Illustrative Black-Scholes premiums or manually entered put-ask and call-bid quotes
- Quote-implied starting volatility when valid market quotes are supplied
- Both options held to expiration
- Dynamic hypothetical option valuation before expiration
- Cash dividends tracked separately
- Scenario, historical-resampling, and historical replay modes
- Adjustable put and call strikes with collar presets
- Strong-rally presets at +30% and +40%
- Opportunity-cost comparison showing unhedged value, collared value, upside given up, and unhedged gain retained
- Steady-rally comparison table at +10%, +20%, +30%, and +40%
- Shaded payoff-chart region showing the short call's upside cost above its strike
- Historical-resampling scenarios built from contiguous three-month blocks of Shiller monthly price returns
- Correct conversion of ordinary historical returns to log returns before recentering and compounding
- Equal historical sampling and deliberately severe-stress-weighted sampling choices
- Optional beta and tracking-error behavior for a proxy equity portfolio
- State-dependent implied volatility and separate put/call skew assumptions
- Severe historical path replays for March 2008 to March 2009 and June 1931 to June 1932

This is an educational scenario model, not an executable quote, forecast, recommendation, or assurance of a portfolio floor. It can accept manually entered quotes but does not validate them against an exchange. It does not account for commissions, exchange fees, market impact, liquidity constraints, taxes, accounting treatment, collateral or margin rules, or management decisions before expiration. Proxy portfolios retain basis risk.

The resampling engine and the two older crisis paths use monthly S&P Composite observations derived from Robert Shiller's long-run market dataset. The simulations use nominal price returns, with dividends modeled separately. Historical replays use interpolated index observations and hypothetical option-pricing assumptions; they are not historical option-chain backtests. Scenario frequencies are not forecast probabilities.

The severe-stress-weighted setting selects a qualifying stress block 35% of the time at each of four quarterly draws. About 82% of those one-year scenarios therefore contain at least one deliberately selected stress block.
