# 04 - Feature Engineering

Encodes ordinal text columns (Education, HasMortgage, HasDependents, HasCoSigner) as ordered numbers, then splits the data into training (70%) and test (30%) sets, stratified on the target so both sets keep the same default rate.

Nominal columns (EmploymentType, MaritalStatus, LoanPurpose) are left as text here and one-hot encoded later inside the modelling pipeline (Module 5), so the encoding is learned only from training data.

## How to run
```bash
pip install pandas numpy scikit-learn
jupyter notebook notebook.ipynb
```

## Input
`../03-data-preprocessing/data/cleaned_data.csv`

## Output
`data/X_train.csv`, `data/X_test.csv`, `data/y_train.csv`, `data/y_test.csv`
