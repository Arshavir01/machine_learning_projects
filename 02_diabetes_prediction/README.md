# Diabetes Prediction

Predict whether a patient has diabetes from 8 medical measurements.

## Dataset
- **Source:** Pima Indians Diabetes Database
- **Size:** 768 patients, 8 features (pregnancies, glucose, blood pressure, skin thickness, insulin, BMI, diabetes pedigree function, age)
- **Target:** `Outcome`, 0 = non-diabetic (500 patients), 1 = diabetic (268 patients)

## Approach
1. Explored the data (shape, class balance, feature means per class).
2. Standardized the features with `StandardScaler`.
3. Stratified train/test split, 80% / 20% (614 train, 154 test).
4. Trained a **Support Vector Machine** (`SVC`, linear kernel).
5. Built a predictive system that standardizes new input before predicting.

## Results
| Metric | Train | Test |
|--------|-------|------|
| Accuracy | 78.7% | 77.3% |

For context, a model that always answers "non-diabetic" would already score about 65% (500 of 768), so the model adds real signal but not a huge amount.

## Limitations and next steps
- The scaler is fitted on the **whole dataset before the split**, so information from the test rows leaks into preprocessing. Fit it on the training set only (for example with a scikit-learn `Pipeline`).
- Glucose, blood pressure, skin thickness and insulin have a minimum of **0**, which is not a real measurement. These are missing values and are not handled yet.
- For a medical problem, accuracy is not enough. Report recall (how many diabetic patients are found), precision and ROC-AUC, and use cross-validation.

## How to run
1. Open `notebook.ipynb` in Google Colab or Jupyter.
2. The notebook reads `diabetes.csv` from `/content/` (the Colab default). Upload the file to your Colab session, or change the path if you run it locally.
3. Install dependencies with `pip install -r ../requirements.txt` (Colab already has most of them).
4. Run all cells.
