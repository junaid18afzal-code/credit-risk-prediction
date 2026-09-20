# 05 - Model Training

Builds a shared preprocessing pipeline (median imputation + scaling for numeric columns, one-hot encoding for categorical columns) and trains 6 classifiers to predict default:

- Logistic Regression
- Ridge-penalised Logistic Regression (L2)
- Lasso-penalised Logistic Regression (L1)
- Decision Tree
- Random Forest
- Gradient Boosting

All models use `class_weight="balanced"` (where supported) since only ~11.6% of borrowers defaulted.

## How to run
```bash
pip install pandas numpy scikit-learn joblib
jupyter notebook notebook.ipynb
```

## Input
`../04-feature-engineering/data/X_train.csv`, `y_train.csv`

## Output
`models/*.joblib` — one trained pipeline per model
