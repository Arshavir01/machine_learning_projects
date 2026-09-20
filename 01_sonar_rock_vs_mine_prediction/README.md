# SONAR: Rock vs Mine Prediction

Classify a sonar signal as a metal cylinder (**mine**) or a **rock**, using 60 signal-strength values.

## Dataset
- **Source:** Sonar, Mines vs. Rocks dataset (UCI Machine Learning Repository)
- **Size:** 208 samples, 60 numeric features
- **Target:** `M` = mine (111 samples), `R` = rock (97 samples)

## Approach
1. Explored the data (shape, class balance, mean of each feature per class).
2. Stratified train/test split, 90% / 10% (187 train, 21 test).
3. Trained a **Logistic Regression** model (scikit-learn defaults).
4. Built a small predictive system that takes 60 values and prints "Rock" or "Mine".

## Results
| Metric | Train | Test |
|--------|-------|------|
| Accuracy | 83.4% | 76.2% (16 of 21 correct) |

## Limitations and next steps
- The test set has only **21 samples**, so one mistake changes accuracy by about 5 points. Use stratified k-fold cross-validation for a steadier estimate.
- Features are not scaled. Scaling and comparing with an SVM or Random Forest would be a natural next step.
- Only accuracy is reported. Add a confusion matrix, precision and recall.

## How to run
1. Open `notebook.ipynb` in Google Colab or Jupyter.
2. The notebook reads `sonar_data.csv` from `/content/` (the Colab default). Upload the file to your Colab session, or change the path if you run it locally.
3. Install dependencies with `pip install -r ../requirements.txt` (Colab already has most of them).
4. Run all cells.
