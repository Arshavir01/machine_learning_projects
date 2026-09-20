# Wine Quality Prediction

Predict whether a red wine is **good quality** from 11 chemical measurements.

## Dataset
- **Source:** Red Wine Quality dataset (UCI Machine Learning Repository)
- **Size:** 1,599 wines, 11 features (acidity, sugar, chlorides, sulfur dioxide, density, pH, sulphates, alcohol and others)
- **Target:** the original quality score (3 to 8) was turned into a binary label: **good** = quality 7 or higher (217 wines), **not good** = below 7 (1,382 wines)

## Approach
1. Explored the data: quality distribution, volatile acidity and citric acid against quality, correlation heatmap.
2. Binarized the quality score.
3. Train/test split, 80% / 20% (1,279 train, 320 test).
4. Trained a **Random Forest Classifier** (default settings).

## Results
| Metric | Test |
|--------|------|
| Accuracy | 93.4% (299 of 320 correct) |

Only 13.6% of the wines are labelled good, so a model that always answers "not good" would score about **86%**. The Random Forest beats that baseline, but accuracy alone does not show how well it finds the good wines.

## Limitations and next steps
- Report precision, recall and F1 for the **good** class, plus a confusion matrix.
- Use a stratified split and `class_weight="balanced"` because the classes are imbalanced.
- Add cross-validation and a feature importance plot (which chemical properties matter most).

## How to run
1. Open `notebook.ipynb` in Google Colab or Jupyter.
2. The notebook reads `winequality-red.csv` from `/content/` (the Colab default). Upload the file to your Colab session, or change the path if you run it locally.
3. Install dependencies with `pip install -r ../requirements.txt` (Colab already has most of them).
4. Run all cells.
