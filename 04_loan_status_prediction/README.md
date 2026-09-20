# Loan Status Prediction

Predict whether a loan application will be approved.

## Dataset
- **Source:** Loan Prediction dataset (loan applications)
- **Size:** 614 applications, 13 columns (gender, marital status, dependents, education, self-employed, applicant and co-applicant income, loan amount, loan term, credit history, property area)
- **Target:** `Loan_Status`, Y = approved, N = not approved

## Approach
1. Removed rows with missing values (614 to 480 rows).
2. Converted text columns to numbers (label encoding) and replaced "3+" dependents with 4.
3. Plotted loan status by education and by marital status.
4. Stratified train/test split, 90% / 10% (432 train, 48 test).
5. Trained a **Support Vector Machine** (`SVC`, linear kernel).

## Results
| Metric | Train | Test |
|--------|-------|------|
| Accuracy | 79.9% | 83.3% (40 of 48 correct) |

## Limitations and next steps
- Dropping rows with missing values throws away about **22%** of the data. Filling the gaps (median for numbers, most frequent value for categories) would keep them.
- The test set has only **48 rows**, and test accuracy is higher than train accuracy. That points to a lucky split, not a better model. Use cross-validation.
- Only accuracy is reported. A wrongly approved loan and a wrongly rejected loan cost different amounts, so add a confusion matrix, precision, recall and F1.
- Features are not scaled, which matters for a linear SVM.

## How to run
1. Open `notebook.ipynb` in Google Colab or Jupyter.
2. The notebook reads `loan_dataset.csv` from `/content/` (the Colab default). Upload the file to your Colab session, or change the path if you run it locally.
3. Install dependencies with `pip install -r ../requirements.txt` (Colab already has most of them).
4. Run all cells.
