# VPBank Young Talents — AI Data Scientist Challenge

**Type:** Individual competition submission
**Role:** Solo — I owned the full pipeline from EDA through model interpretation and business recommendation.

## Problem

VPINS (VPBank's insurance division) wanted to run an efficient sales campaign for a healthcare policy (AIA).
Given an 86-attribute customer dataset (5,822 training records: 42 sociodemographic + 43 product-ownership
attributes), predict which customers are likely to purchase the policy, then hand the division manager a
short, prioritised list of the customers most worth targeting. The target variable is **severely imbalanced**
— the large majority of customers do not purchase.

The brief had two explicit deliverables, scored separately:
1. **Prediction task** — filter the 4,000-customer test set down to the 800 most promising cases (validated
   against a held-out label set the team didn't have access to).
2. **Explanation task** — scored specifically on **comprehensibility, usefulness, and actionability** for the
   division manager, not just technical accuracy. This is why the SHAP interpretability step wasn't
   optional — it was graded criteria, not a nice-to-have.

## Approach

1. Applied **SMOTE** oversampling to address the class imbalance before training.
2. Benchmarked **7 algorithms** (Logistic Regression, Decision Tree, Random Forest, SVM, Naive Bayes,
   XGBoost, LightGBM).
3. Selected XGBoost and tuned it via grid search across 5 hyperparameters (learning rate, max depth,
   n_estimators, subsample, colsample_bytree).
4. Applied **SHAP** for model interpretability to identify which features actually drove predictions.
5. Reported **AUC-ROC** rather than accuracy as the headline metric — with ~94% of customers in the
   majority class, accuracy alone would be misleading.
6. Translated the ranked output into a shortlist of the top 800 highest-propensity customers out of a
   4,000-customer test pool.

## Results

| Metric | Value |
|---|---|
| AUC-ROC | 0.93 |
| Algorithms benchmarked | 7 |
| Features in dataset | 86 |
| Customers shortlisted | 800 of 4,000 |

## Files

- `notebooks/01_EDA.ipynb` — exploratory data analysis
- `notebooks/02_Model.ipynb` — SMOTE, model benchmarking, XGBoost tuning, SHAP analysis
- `AI_DATA_SCIENTIST_CHALLENGE_brief.pdf` — original task brief from VPBank/VPINS
- `attributes_description.pdf` — data dictionary for the 86 features (based on the COIL 2000 insurance
  dataset structure)
- `top_800_customers_output.csv` — final shortlisted customer output

## Full write-up

[Case study on Notion](https://app.notion.com/p/3c2c83dfa32d8153aa4af1e8899b7387) — includes the full
narrative, methodology diagram, and what I'd highlight in an interview.
