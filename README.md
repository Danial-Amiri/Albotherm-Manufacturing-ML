# Manufacturing Process Optimisation — Predictive Modelling for Albotherm Technology

A machine learning project developed in collaboration with **Albotherm Technology (UK)** as part of the MSc Data Science Interdisciplinary Group Project at the University of the West of England, Bristol.

## Project Overview

Albotherm produces micro-particles with a liquid core and solid shell used in manufacturing additives. Physical experiments are costly and time-consuming. The goal of this project was to build a predictive model that allows engineers to input process parameters and predict product quality outcomes — specifically dryness after 24 hours — before committing to a physical run.

## My Contribution

This repository contains my personal contributions to the group project:

- **`Prediction_Model_Danial.ipynb`** — Full ML pipeline: data loading, EDA, missing value handling, feature engineering, model training, benchmarking, and evaluation
- **`GUI__Danial.ipynb`** — A Tkinter-based desktop prediction tool that loads the trained model and allows engineers to enter process parameters and receive instant quality predictions with confidence indicators

## What the Model Does

- Takes manufacturing process parameters as input (viscosity, flow rates, UV power, curing energy, formulation type etc.)
- Predicts **% dry after 24 hours** — the key quality metric for Albotherm's manufacturing process
- Highlights the most important parameters driving product outcomes

## Methodology

### Data & Preprocessing
- Real experimental manufacturing dataset provided by Albotherm
- Handled missing values using **KNN Imputation**
- Applied feature engineering to derive key ratio-based variables
- Encoded categorical manufacturing parameters (formulations, equipment used)

### Feature Selection & Importance
- Applied **permutation importance** and **SelectFromModel** to identify the most critical process parameters
- Key finding: **viscosity ratios** (emulsion/core) and **UV power** were the strongest predictors of dryness outcomes

### Models Benchmarked
| Model | Notes |
|---|---|
| Random Forest Regressor | Best overall performance |
| Gradient Boosting Regressor | Strong alternative |
| XGBoost | Tested with hyperparameter tuning |
| ElasticNet / Lasso | Linear baselines |

- Hyperparameter tuning via **RandomizedSearchCV** with cross-validation
- Final model selected on R² and MAE across held-out test set

### Prediction GUI
Built with **Tkinter** — a desktop tool that:
- Loads the trained model
- Accepts both numerical and categorical process parameters
- Allows engineers to select only the parameters they have available
- Returns a predicted dryness value with a confidence score
- Highlights the top 5 most influential input parameters

## Tech Stack

```
Python · Scikit-Learn · XGBoost · Pandas · NumPy · Matplotlib · Seaborn · Tkinter · Joblib
```

## Project Context

This was a real industry partnership — Albotherm provided their experimental dataset and defined the business problem. The deliverable was a working prediction tool that their team could use to make data-driven go/no-go decisions before running physical experiments.

**University:** University of the West of England, Bristol  
**Programme:** MSc Data Science  
**Academic Year:** 2024–2025
