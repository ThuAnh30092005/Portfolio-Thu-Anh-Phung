# Recommendation System — MovieLens 1M

**Type:** Personal project
**Role:** Solo, built to compare recommendation approaches rather than to optimise a single metric.

## Problem

Most recommendation-system tutorials show one technique. This project compares four major approaches on
the same dataset — 1,000,209 ratings from 6,040 users across ~3,900 movies.

## Approach

1. **Collaborative filtering** — matrix factorization via ALS and SVD.
2. **Content-based filtering** — TF-IDF vectorization of movie genres + cosine similarity (works for
   brand-new users/movies with no rating history — solves the "cold-start" problem the other methods can't).
3. **Unsupervised clustering** — K-Means, hierarchical clustering, and DBSCAN to segment users into
   behavioural groups, validated with dendrogram analysis.
4. **Supervised baseline** — a Random Forest regressor predicting rating from demographic features (age,
   gender, occupation) plus genre.

## An honest note on results

Earlier drafts of my CV cited a specific RMSE/MAE for this project that I could not verify against the
saved notebook output. The ALS run produced a high RMSE (~3.25), the SVD cell's output wasn't saved, and
only the Random Forest baseline (RMSE ~1.11) has a verifiable number. Rather than guess, this README
reports the comparison itself — the value of this project is in the trade-off analysis between approaches,
not a single leaderboard number.

## Files

- `notebooks/recommendation_system.ipynb` — all 4 approaches, with EDA and evaluation

## Full write-up

[Case study on Notion](https://app.notion.com/p/3c2c83dfa32d817a85e1ec8552bf6556)
