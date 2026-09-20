# 03 - Data Preprocessing

Cleans the raw data: checks for duplicate rows, checks for data leakage ("cheating" columns too strongly correlated with the target), and drops the non-predictive `LoanID` column.

## How to run
```bash
pip install pandas numpy
jupyter notebook notebook.ipynb
```

## Input
`../01-data-collection/data/Loan_default.csv`

## Output
`data/cleaned_data.csv`
