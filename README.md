# NBA Player Performance Forecasting with Deep Learning

This repository contains my **Master’s dissertation project** on forecasting future NBA player performance using deep learning and historical player-season statistics.

**Dissertation title:** *Predicting NBA Players Future Value Over Replacement Player using Deep Learning*  
**Author:** Rajat Choudhary  
**Degree:** MSc, University of Glasgow  
**Outcome:** Awarded **A3**

## Overview

Predicting how NBA players will perform in future seasons is an important problem in sports analytics. Teams make high-stakes decisions based on player value, including contract renewals, trade negotiations, roster construction, and long-term development planning.

This project studies that problem using deep learning on historical NBA player data and makes two main contributions:

1. It improves on a recent state-of-the-art deep learning benchmark for player-performance prediction.
2. It argues that **Value Over Replacement Player (VORP)** is a more meaningful target variable than **Win Shares (WS)** for this task.

The work combines:
- a full dissertation,
- the modelling notebook,
- the source datasets,
- and a glossary of basketball/statistical terms.

## Why this project matters

A player’s future performance affects much more than just box-score expectations. It can influence:
- how valuable that player is to an organization,
- whether they should receive a larger future contract,
- whether their decline should trigger coaching intervention,
- and how much value they hold in trade scenarios.

This dissertation was motivated by exactly those practical questions.

The significance of the study is not only that it predicts player performance, but that it shows **how target choice changes the usefulness of the model**. Instead of only predicting **Win Shares**, this project proposes **VORP** as a stronger measure of player value because it reflects a player’s contribution relative to a replacement-level player, tracks more naturally with value to a team, and can support reasoning about salary, trade value, and team impact.

## Main contribution

This dissertation builds on a 2021 study on NBA player-performance prediction and shows that deep learning can perform better when trained on a richer input structure with more predictor variables.

The main findings are:

- All three tested deep learning models improved the prior state-of-the-art for predicting **Win Shares**.
- The best **Win Shares** result came from the **2-layer neural network**, with:
  - **MAE = 0.1231**
  - **MSE = 0.0310**
- The best **VORP** result came from the **3-layer neural network**, with:
  - **MAE = 0.0354**
  - **MSE = 0.0022**
- Every model performed better when predicting **VORP** rather than **Win Shares**.
- Compared with the previous benchmark MSE of **4.32**, the best model improved the error by **4.2890**.

## Why VORP was proposed

A central part of the dissertation is the argument that **VORP** is a better target for judging and forecasting player performance than **Win Shares**.

The reasons include:

- VORP reflects a player’s value **relative to a replacement-level player**.
- It captures a player’s contribution more directly in terms of team value.
- It is more useful for practical decision-making around:
  - salary valuation,
  - trade assessment,
  - roster planning,
  - and the impact of losing or replacing a player.

In the dissertation, VORP was not only argued to be more meaningful conceptually, but also shown to be **more predictable** in this modelling setup.

## Repository contents

- `Dissertation.pdf`  
  Full dissertation report, including motivation, background, methodology, evaluation, and conclusion.

- `NBA_future_performance_submission.ipynb`  
  Main notebook containing the end-to-end workflow for preprocessing, modelling, and evaluation.

- `Glossary.xlsx`  
  Supporting glossary for basketball statistics and variables.

- `Players.csv`  
  Player metadata used in dataset construction.

- `Seasons_Stats.csv`  
  Historical NBA season statistics.

- `player_data.csv`  
  Additional player-level data used in building the modelling dataset.

## Project objective

The objective of this dissertation was to improve deep learning performance in forecasting NBA player performance and to test whether a better target variable could improve both prediction quality and decision relevance.

The project compares three neural-network architectures:

- **2-layer neural network**
- **3-layer neural network**
- **3-layer neural network with additional nodes**

Each model is evaluated on two target variables:

- **Win Shares (WS)**
- **Value Over Replacement Player (VORP)**

## Data and preprocessing

The study uses NBA player data drawn from historical season statistics and combines both:

- **basic box score statistics**
- **advanced statistics**

The final dataset includes a richer feature set than the earlier baseline study, with **49 features** used to describe player performance.

Key preprocessing decisions included:
- removing seasons before 1980,
- excluding very low-game-count cases,
- fixing percentage features where no attempts occurred,
- cleaning player names,
- encoding player position,
- and one-hot encoding categorical variables such as team and player.

## Methodology

The models were implemented using **Keras** and **TensorFlow**.

The evaluation design included:
- a **70:30 train/test split**,
- **10-fold cross-validation** on the training data,
- and **10 repeated evaluation experiments** to reduce the effect of stochastic variation in deep learning training.

This repeated-evaluation setup was used because neural-network training is inherently stochastic, and the dissertation explicitly aimed to produce more stable estimates of model performance.

## Results summary

### Best results for Win Shares
- **Best model:** 2-layer neural network
- **Test MAE:** 0.1231
- **Test MSE:** 0.0310

### Best results for VORP
- **Best model:** 3-layer neural network
- **Test MAE:** 0.0354
- **Test MSE:** 0.0022

### Comparative significance
- Every model produced **lower error** on **VORP** than on **Win Shares**.
- This suggests that **VORP is both a more meaningful and more learnable target** for this forecasting problem.
- Relative to the previous study’s MSE benchmark of **4.32**, the best model improved the error by **4.2890**.

## Significance of the study

This dissertation is significant in two ways.

### 1. Methodological significance
It demonstrates that deep learning can improve NBA player-performance forecasting when trained on a richer data structure than the prior benchmark study.

### 2. Practical significance
It shows that **predicting VORP may be more useful than predicting Win Shares** for real basketball decision-making.

This matters because VORP gives a clearer estimate of how valuable a player is relative to a replacement-level player. That makes the prediction more relevant for:
- contracts,
- trade value,
- roster management,
- and strategic team planning.

In other words, the dissertation does not only improve model accuracy; it also improves the **usefulness of what is being predicted**.

## What makes this repository stronger than a typical notebook repo

This repository is not just code. It includes:

- the dissertation itself,
- the modelling notebook,
- the data files,
- and a glossary.

That makes it a more complete academic project and provides the full research context behind the modelling choices and conclusions.

## Tools and libraries

Main tools used in this project include:
- Python
- Pandas
- NumPy
- TensorFlow / Keras
- Matplotlib
- Seaborn

## Limitations and future work

The dissertation also discusses several improvements that could strengthen the work further:

- adding even richer player and game-related features,
- extending the data beyond 2017,
- tuning hyperparameters more systematically,
- increasing evaluation repetitions for stability,
- and incorporating broader team-context variables such as coaching, cohesion, and organization-level effects.

These are important because basketball is a team sport, and player performance is shaped by more than individual box-score history alone.

## Suggested GitHub description

**Master’s dissertation on forecasting future NBA player performance with deep learning, improving a prior benchmark and proposing VORP as a more meaningful target than Win Shares.**

## Suggested topics

`sports-analytics` `deep-learning` `nba` `basketball-analytics` `tensorflow` `regression` `dissertation` `player-forecasting`

## Author

**Rajat Choudhary**
