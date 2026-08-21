# ASBA Predictive Analytics — Airbnb Price Prediction

**Type:** Competition, 3-person team
**Role:** I owned **Task 2 — data cleaning and feature engineering**. A teammate owned Task 1 (EDA) and
another owned Task 3 (model selection and hyperparameter tuning). I collaborated with the team on Task 3
but did not personally implement the tuning — this README and the notebook reflect my actual scope.

## Problem

Predict the nightly price of Airbnb listings in Melbourne (3,735 training records, 1,601 test records) from
raw, inconsistently formatted scraped data — 80+ attributes covering host behaviour, property
characteristics, and review history.

## Approach (my scope — Task 2)

1. Cleaned numeric fields stored as mixed-type strings (percentages, currency symbols) across host
   response rate, acceptance rate, and related fields.
2. Built the missing-value imputation strategy across 80+ attributes — median for numeric fields,
   mode-based for categorical fields.
3. Engineered 4+ new features, including a composite average review score, and applied manual/ordinal
   encoding for categorical variables such as host response time.
4. Applied **TextBlob sentiment analysis** on listing name, description, and host bio text.
5. Built feature scaling (StandardScaler) ahead of handoff to the modelling stage.

## Results

The team's final model (Random Forest / XGBoost / Ridge, tuned by a teammate) achieved an **MAE of 277.86**
on the competition leaderboard. My contribution was the data foundation the model was trained on.

## Files

- `notebooks/airbnb_data_cleaning_feature_engineering.ipynb` — full team notebook (my sections: Task 2)
- `metadata.csv` — data dictionary for the raw listing attributes

## Full write-up

[Case study on Notion](https://app.notion.com/p/3c2c83dfa32d81f9a71be8f08cd29e0e) — includes the full
narrative and an honest breakdown of team scope.
