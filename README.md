# Credit Risk Prediction

Machine learning project predicting loan default risk from 255,347 consumer loan applications, comparing 6 classification models and analysing the accuracy-vs-recall trade-off on an imbalanced dataset (11.6% default rate).

## Key finding

Accuracy alone is misleading on imbalanced data. Gradient Boosting scores highest on accuracy (~88.6%) but catches only ~5% of actual defaulters. Logistic Regression scores lower on accuracy (~67.7%) but catches ~70% of actual defaulters — the metric that matters most to a lender trying to avoid losses. See [`06-model-evaluation`](06-model-evaluation/) for the full comparison.

## Tech stack

Python, pandas, NumPy, scikit-learn, matplotlib, seaborn, Jupyter

## Project structure

Each module is a self-contained step in the pipeline, with its own notebook, README, and inputs/outputs:

| Module | What it does |
|---|---|
| [01-data-collection](01-data-collection/) | Load the raw dataset and take a first look |
| [02-exploratory-analysis](02-exploratory-analysis/) | Summary statistics, correlation heatmap, charts |
| [03-data-preprocessing](03-data-preprocessing/) | Check duplicates and data leakage, drop the ID column |
| [04-feature-engineering](04-feature-engineering/) | Encode ordinal columns, stratified train/test split |
| [05-model-training](05-model-training/) | Train 6 classifiers with a shared preprocessing pipeline |
| [06-model-evaluation](06-model-evaluation/) | Score every model, inspect the simplest model's coefficients |

Each notebook reads its input from the previous module's output folder, so they can be run in order (01 → 06) to reproduce the full pipeline.

## How to run

```bash
git clone https://github.com/junaid18afzal-code/credit-risk-prediction.git
cd credit-risk-prediction
pip install -r requirements.txt
```

Then open each module's `notebook.ipynb` in order and run all cells (Jupyter or VS Code).

## Dataset

`Loan_default.csv` — 255,347 consumer loan applications with 18 features (age, income, loan amount, credit score, employment, etc.) and a binary target `Default`.

## What this project demonstrates

- Data cleaning and leakage checks before modelling
- Correct handling of ordinal vs. nominal categorical variables
- A leak-free pipeline (all preprocessing fit only on training data)
- Comparing multiple models on an imbalanced classification problem
- Choosing the right metric (Recall, not just Accuracy) for the business problem
- Model interpretability via Logistic Regression coefficients

## Caveats

- Coefficients show association, not causation.
- Results come from one dataset; a different lender or time period could differ.
- Default model hyperparameters were used — no tuning was performed.
