# 06 - Model Evaluation

Scores every trained model on the held-out test set using Accuracy, Precision, Recall, F1, and ROC-AUC, then inspects which features matter most to the Logistic Regression model.

## Key finding
Gradient Boosting has the highest accuracy (~88.6%) but only catches ~5% of actual defaulters (Recall). Logistic Regression has lower accuracy (~67.7%) but catches ~70% of actual defaulters. Accuracy alone is misleading on this imbalanced dataset (88% vs 12%) — Recall and the confusion matrix tell the real story.

## How to run
```bash
pip install pandas numpy scikit-learn joblib
jupyter notebook notebook.ipynb
```

## Input
`../04-feature-engineering/data/X_test.csv`, `y_test.csv`
`../05-model-training/models/*.joblib`

## Output
`output/model_comparison.csv`
