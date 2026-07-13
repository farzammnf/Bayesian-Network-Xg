# Bayesian Network for Predicting Goal Probability (xG)

This project builds an expected goals (xG) model using StatsBomb Open Data. It compares an Expert Bayesian Network, a Hill-Climbing Bayesian Network, Logistic Regression, Random Forest feature analysis, and the StatsBomb xG benchmark.

## Files

- `notebooks/extracting-data.ipynb`: downloads and prepares StatsBomb event data.
- `notebooks/analysis.ipynb`: full EDA, feature engineering, Bayesian Network modeling, evaluation, and query checks.
- `report/report.pdf`: final project report.
- `slides/presentation.pdf`: project presentation slides.
- `figures/`: saved figures used in the report and notebook.

## Dataset

StatsBomb Open Data: https://github.com/statsbomb/open-data

## Main idea

The target is:

```math
P(Goal = Yes \mid shot\ information)
