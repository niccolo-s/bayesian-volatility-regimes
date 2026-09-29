# Time-Varying Volatility versus Heavy Tails in S&P 500 Returns

A Bayesian analysis of S&P 500 volatility with PyMC. Full details are in the report: [`report.pdf`](report.pdf).

**Questions.**
1. Are the heavy tails of returns simply a consequence of volatility changing over time?
2. Does splitting the market into "normal" and "crisis" regimes help forecast volatility?

**Findings.**
- Stochastic volatility models on weekly returns (2005–2025) show a strongly time-varying, persistent volatility (half-life of about 14 weeks). Once volatility varies, the return shocks are close to Normal (Student-t degrees of freedom above 10), so the heavy tails come mainly from changing volatility.
- A threshold AR(1) model for daily log realized volatility performs the same as a single-regime AR(1) out of sample (2023–2025), and both are only marginally better than the naive persistence forecast. Its crisis signal is lagged by construction.

## Repository structure

```
├── code_v2.ipynb      # main analysis (used in the report): weekly SV models, daily threshold model
├── code_v1.ipynb      # exploratory analysis on monthly returns (not part of the report)
├── data/              # frozen snapshot of daily S&P500 prices, 2005–2025 (+ download metadata)
├── plots/, plots2/    # figures produced by code_v1 and code_v2
├── report.pdf         # project report
├── CORRECTIONS.md     # corrections to the original version, with motivations and references
└── requirements.txt   # pinned package versions
```

The notebooks never download data: every result is reproducible from the snapshot in `data/`.

## How to run

Requires Python ≥ 3.11 (tested with 3.13).

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
```

Run the notebooks from the repository root, top to bottom. Sampling uses a fixed random seed (42).

## Origin

Revised version of a group project for the *AI Programming* course at TU Wien, originally developed with M. Csikós. The original version is in the git history; all changes are documented in [`CORRECTIONS.md`](CORRECTIONS.md).
