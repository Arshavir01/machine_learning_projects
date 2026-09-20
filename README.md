# Machine Learning Projects

Eight machine learning projects with scikit-learn (plus one with XGBoost), built while learning classification and regression. Each project has its own folder with a notebook and a README that explains the data, the approach, the results and what could be improved.

## Projects

| # | Project | Task | Model | Test result |
|---|---------|------|-------|-------------|
| 1 | [SONAR Rock vs Mine](01_sonar_rock_vs_mine_prediction/) | Classification | Logistic Regression | 76.2% accuracy |
| 2 | [Diabetes Prediction](02_diabetes_prediction/) | Classification | SVM (linear) | 77.3% accuracy |
| 3 | [House Price (California)](03_house_pricing_prediction/) | Regression | XGBoost | R² 0.834, MAE 0.311 |
| 4 | [Loan Status Prediction](04_loan_status_prediction/) | Classification | SVM (linear) | 83.3% accuracy |
| 5 | [Wine Quality Prediction](05_wine_quality_prediction/) | Classification | Random Forest | 93.4% accuracy |
| 6 | [Car Price Prediction](06_car_price_prediction/) | Regression | Linear Regression, Lasso | R² 0.837 (Linear), 0.871 (Lasso) |
| 7 | [Gold Price Prediction](07_gold_price_prediction/) | Regression | Random Forest | R² 0.989 |
| 8 | [Heart Disease Prediction](08_heart_disease_prediction/) | Classification | Logistic Regression | 82.0% accuracy |

## A note on these results

Most datasets here are small, and four of the projects (SONAR, Loan, Car, Heart) have test sets of only about 20 to 60 rows, so a single train/test split gives a noisy estimate. Each project README lists its limitations, such as small test sets, missing cross-validation and metrics beyond accuracy, so the results are read in the right context.

## How to run

1. Clone the repo: `git clone https://github.com/Arshavir01/machine_learning_projects.git`
2. Install the dependencies: `pip install -r requirements.txt`
3. Open a project's `notebook.ipynb` in Jupyter or Google Colab and run all cells. Each project README says which dataset file the notebook needs.

## Tech

Python, pandas, NumPy, scikit-learn, XGBoost, Matplotlib, Seaborn

## Author

Arshavir Voskanyan
