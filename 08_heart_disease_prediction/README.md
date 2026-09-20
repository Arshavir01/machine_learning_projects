# Heart Disease Prediction

Predict whether a patient has heart disease from 13 clinical measurements.

## Dataset
- **Source:** Heart Disease dataset (UCI Cleveland data, as used on Kaggle)
- **Size:** 303 patients, 13 features (age, sex, chest pain type, resting blood pressure, cholesterol, fasting blood sugar, ECG results, max heart rate, exercise-induced angina, ST depression and others)
- **Target:** `target`, 1 = heart disease (165 patients), 0 = healthy (138 patients)
- No missing values.

## Approach
1. Explored the data (shape, types, missing values, class balance).
2. Stratified train/test split, 80% / 20% (242 train, 61 test).
3. Trained a **Logistic Regression** model.
4. Built a small predictive system for one new patient.

## Results
| Metric | Train | Test |
|--------|-------|------|
| Accuracy | 85.1% | 82.0% (50 of 61 correct) |

## Limitations and next steps
- Training printed a **convergence warning**. Scale the features with `StandardScaler` and increase `max_iter`.
- The test set has only **61 patients**. Use cross-validation for a steadier estimate.
- In a medical setting, missing a sick patient is the costly mistake. Report recall (sensitivity), precision, ROC-AUC and a confusion matrix, not only accuracy.
- Try Random Forest or gradient boosting and show feature importance.

## How to run
1. Open `notebook.ipynb` in Google Colab or Jupyter.
2. The notebook reads `heart_disease_data.csv` from `/content/` (the Colab default). Upload the file to your Colab session, or change the path if you run it locally.
3. Install dependencies with `pip install -r ../requirements.txt` (Colab already has most of them).
4. Run all cells.
