# Gold Price Prediction

Predict the price of the gold ETF (**GLD**) from other market indicators.

## Dataset
- **Source:** Gold Price dataset (`gld_price_data.csv`), daily market data from 2008 to 2018
- **Size:** 2,290 daily records
- **Columns:** `SPX` (S&P 500), `GLD` (gold ETF, the target), `USO` (oil ETF), `SLV` (silver ETF), `EUR/USD`

## Approach
1. Checked for missing values (none) and calculated correlations with GLD: SLV 0.87, USO -0.19, SPX 0.05, EUR/USD -0.02.
2. Used SPX, USO, SLV and EUR/USD as features.
3. Random train/test split, 80% / 20%.
4. Trained a **Random Forest Regressor** (100 trees) and plotted actual vs predicted values.

## Results
| Metric | Test |
|--------|------|
| R² | 0.989 |

## Limitations and next steps
- This is **time-series data split randomly**, so the model is tested on days that sit between training days. The R² of 0.989 is therefore optimistic. A realistic check trains on earlier years and tests on later years.
- SLV (silver) is strongly linked to gold and is measured on the **same day**, so this is not really forecasting. Compare against a simple baseline such as "tomorrow's price = today's price".
- Try lag features (previous days' prices) and a chronological split.

## How to run
1. Open `notebook.ipynb` in Google Colab or Jupyter.
2. The notebook reads `gld_price_data.csv` from `/content/` (the Colab default). Upload the file to your Colab session, or change the path if you run it locally.
3. Install dependencies with `pip install -r ../requirements.txt` (Colab already has most of them).
4. Run all cells.
