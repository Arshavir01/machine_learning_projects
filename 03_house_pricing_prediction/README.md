# House Price Prediction (California Housing)

Predict the median house value of a California district from census data.

## Dataset
- **Source:** California Housing dataset, loaded with `sklearn.datasets.fetch_california_housing`
- **Size:** 20,640 districts, 8 features (median income, house age, average rooms, average bedrooms, population, average occupancy, latitude, longitude)
- **Target:** median house value, in units of $100,000
- No missing values.

## Approach
1. Explored the data and plotted a correlation heatmap.
2. Train/test split, 80% / 20% (16,512 train, 4,128 test).
3. Trained an **XGBoost Regressor** with default hyperparameters.
4. Evaluated with R² and mean absolute error (MAE), and plotted actual vs predicted prices.

## Results
| Metric | Train | Test |
|--------|-------|------|
| R² | 0.944 | 0.834 |
| MAE | 0.193 | 0.311 (about $31,100) |

## Limitations and next steps
- The gap between train R² (0.94) and test R² (0.83) shows the model **overfits**. Tune `max_depth`, `learning_rate` and `n_estimators`, and use early stopping.
- No baseline yet. Compare with Linear Regression and Random Forest to show how much XGBoost really adds.
- Add cross-validation and a feature importance plot to explain which features drive the price.

## How to run
1. Open `notebook.ipynb` in Google Colab or Jupyter.
2. The dataset is downloaded automatically by scikit-learn, no file needed.
3. Install dependencies with `pip install -r ../requirements.txt` (Colab already has most of them).
4. Run all cells.
