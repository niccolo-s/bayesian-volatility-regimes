# Bayesian Time Series Analysis with Probabilistic Programming

This project applies Bayesian probabilistic programming to model the volatility dynamics of the S&P 500 index.  
The analysis is split into two phases: a **long‑term trend model** on monthly data with regime‑switching volatility, and a **high‑frequency volatility model** on daily data that distinguishes normal and crisis regimes.  
The goal is to understand whether apparent “fat tails” in returns are better explained by heavy‑tailed likelihoods or by explicit modeling of time‑varying volatility, and to evaluate the models in an out‑of‑sample forecasting setting.

## Repository structure

- `code_v1.ipynb`  
  Notebook for **Phase 1** of the project.  
  Contains data loading, preprocessing of monthly prices, specification and fitting of piecewise‑linear trend models with different volatility assumptions, and out‑of‑sample forecasting on the test period.

- `code_v2.ipynb`  
  Notebook for **Phase 2** of the project.  
  Works with daily data, builds realized volatility, fits a regime‑switching AR(1) model for log‑volatility, and evaluates forecasting performance and crisis detection on unseen data.

- `data/`  
  Input datasets used in the analysis (price series and derived time series).

- `plots/`  
  Figures generated in Phase 1 (trend fits, posterior summaries, forecast plots, etc.).

- `plots2/`  
  Figures generated in Phase 2 (volatility paths, predictive intervals, regime classification plots).

- `report.pdf`  
  Full project report describing the methodology, models, results, and references.

- `requirements.txt`  
  List of Python dependencies needed to run the notebooks.
