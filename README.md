# Gold Price Forecasting System (Data System)

## Overview
End-to-end data system that ingests market + macro data (Gold, Bitcoin, USD index, CPI / rates / unemployment),
stores it in a PostgreSQL warehouse, trains ML models, and serves forecasts through a Streamlit dashboard.

## Key Ideas
- Automated ingestion from Yahoo Finance + FRED
- Orchestrated ELT pipeline (Airflow) with raw storage (MinIO) + structured warehouse (PostgreSQL)
- Dashboard-first workflow: explore → train models → generate forecasts → export results

## System Architecture
**Stack:** Yahoo Finance + FRED → Airflow → MinIO (raw) → PostgreSQL (warehouse) → Streamlit (UI)

## Features
- Data Exploration: preview indicators, summary stats, correlations
- Model Training: train & compare (Random Forest / Gradient Boosting / XGBoost) using RMSE, MAE, R²
- Prediction: choose model + forecast horizon (1–365 days) and export predictions to CSV
- Privacy-by-design: local access without storing user credentials in the warehouse

## Files
- `docs/report.pdf` — Full implementation report (architecture, schema, task flows, UI design, testing)

## Repo Structure
- `docs/` reports and documentation

## Notes
This repository is documentation-first for portfolio review.
If you want to publish runnable code later, add:
- `src/` pipeline scripts / modelling code
- `docker/` compose + env templates
- `requirements.txt`
