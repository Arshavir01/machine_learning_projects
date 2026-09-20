# Car Price Prediction

Predict the selling price of a used car and compare two regression models.

## Dataset
- **Source:** CarDekho used car data
- **Size:** 301 cars, features: year, present price, kilometers driven, fuel type (Petrol / Diesel / CNG), seller type, transmission, number of owners
- **Target:** `Selling_Price`

## Approach
1. Checked for missing values (none) and looked at the categorical columns.
2. Encoded fuel type, seller type and transmission as numbers, and dropped the car name.
3. Train/test split, 90% / 10% (about 30 test cars).
4. Trained and compared **Linear Regression** and **Lasso Regression**, using R².

## Results
| Model | Train R² | Test R² |
|-------|----------|---------|
| Linear Regression | 0.880 | 0.837 |
| Lasso Regression | 0.843 | 0.871 |

## Limitations and next steps
- With only about 30 test cars, Lasso beating Linear Regression on the test set could be luck. Compare the models with cross-validation.
- Fuel type is encoded as 0, 1, 2, which suggests an order that does not exist. One-hot encoding is more correct.
- Lasso is sensitive to feature scale and was used with the default `alpha`. Scale the features and tune `alpha`.
- Add MAE or RMSE next to R², and try tree-based models such as Random Forest.

## How to run
1. Open `notebook.ipynb` in Google Colab or Jupyter.
2. The notebook reads `car data.csv` from `/content/` (the Colab default). Upload the file to your Colab session, or change the path if you run it locally.
3. Install dependencies with `pip install -r ../requirements.txt` (Colab already has most of them).
4. Run all cells.
