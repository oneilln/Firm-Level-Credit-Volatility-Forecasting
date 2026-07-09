# Firm-Level-Credit-Volatility-Forecasting
MSc Finance dissertation code: Firm-level tests of whether credit signals forecast equity volatility, using HAR, GJR-GARCH and machine learning models on 56 US firms, 2010-2024.
# Overview
This repository contains the code accompanying my MSc Finance dissertation at Trinity Business School (2026), titled “Distress, Leverage, and the Predictive Content of Credit Signals for Equity Volatility”. 
# Data
The forecasting notebooks read “Panel.parquet” and “Sector_Composites.parquet” directly, so the modelling pipeline is runnable from the repository as shipped. Every table and figure in the dissertation is produced from these two files.
The raw source files are Bloomberg exports (single-name 5-year CDS spreads, firm equity prices, SPDR ETF prices, VIX, 2 and 10 year US Treasury yields) and one FRED series (Moody's Baa corporate spread). Bloomberg data cannot be redistributed, so the raw files are not included. The three data construction notebooks are included nonetheless for replicability. 
# Running the code
Clone the repository, then from any Python environment with the packages listed below installed:
```bash
git clone https://github.com/oneilln/Firm-Level-Credit-Volatility-Forecasting.git
cd Firm-Level-Credit-Volatility-Forecasting/forecasting
jupyter notebook
```
Open each notebook in the order. Each is self-contained and reads from `../data/`. Restart the kernel and Run All to reproduce every table in Chapter 4 and Appendix D of the dissertation.
# Required packages
•	pandas, numpy, scipy
•	scikit-learn
•	xgboost
•	shap
•	arch (for GJR-GARCH)
•	statsmodels
•	openpyxl (for the data-construction notebooks only)
•	jupyter
# Reproducibility
Random Forest and XGBoost results carry roughly 0.5% run-to-run stochastic variation, which does not affect the paper's headline findings. The notebooks reflect the corrected sample; an EXE contamination was identified and removed.
