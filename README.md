# Bayesian Network for Predicting Goal Probability (xG)

This project builds an interpretable expected goals (xG) model for football shots using **StatsBomb Open Data** and **Bayesian Networks**.

The target is:

`P(Goal = Yes | shot evidence)`

The project compares an **Expert Bayesian Network**, a **Hill-Climbing Bayesian Network**, **Logistic Regression**, **Random Forest feature analysis**, and the **StatsBomb xG benchmark**.

## Overview

Expected goals (xG) assigns each shot a probability of becoming a goal. Instead of only counting goals or shots, xG estimates the quality of a scoring chance.

This project uses shot-level event data and freeze-frame information to model goal probability from:

- shot distance and angle
- goalkeeper location and context
- teammate and opponent locations
- nearby-player pressure
- shot-triangle features
- body part, technique, shot type, and play pattern

StatsBomb xG was **not used for training**. It was used only as an external benchmark.

## Dataset

Dataset: [StatsBomb Open Data](https://github.com/statsbomb/open-data)

The processed dataset contains more than 100,000 shots, with an empirical goal rate of approximately **11.16%**.

## Models

### Expert Bayesian Network

A manually designed Bayesian Network based on football knowledge. It uses interpretable intermediate variables such as:

- `GeometryQuality`
- `ShotExecution`
- `DefensivePressure`
- `GoalkeeperContext`

### Hill-Climbing Bayesian Network

A data-driven Bayesian Network structure learned with score-based Hill-Climbing. A Markov blanket analysis was also used to study the local dependencies around `Goal`.

### Baselines and comparison models

- Logistic Regression xG baseline
- Random Forest feature importance
- StatsBomb xG benchmark

## Main Findings

The analysis showed that goal probability is strongly influenced by:

- shot angle
- distance to goal
- distance to the goalkeeper
- goalkeeper context
- shot geometry quality

Bayesian Networks were useful not only for prediction, but also for interpretable probability queries, such as estimating the goal probability of:

- an open-goal chance
- a high-quality close shot
- a header from a corner under pressure
- a difficult long-range shot

## Repository Structure

```text
.
├── extracting-data.ipynb
├── analysis.ipynb
├── report.pdf
├── slides/
│   └── presentation.pdf
├── figures/
│   └── saved figures used in the report and notebooks
└── README.md
