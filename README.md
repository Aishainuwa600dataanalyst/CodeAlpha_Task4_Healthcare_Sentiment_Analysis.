# CodeAlpha Task 4: Healthcare Drug Review Sentiment Analysis

Sentiment classification of patient drug reviews (Positive / Neutral / Negative), comparing
**Logistic Regression** and **LinearSVC** on TF-IDF text features. Built for the CodeAlpha
machine learning internship (Task 4).

![Model comparison](https://github.com/Aishainuwa600dataanalyst/CodeAlpha_Task4_Healthcare_Sentiment_Analysis./blob/main/model_comparison.png)

## Results

Evaluated on 829 held-out reviews (class counts: 560 Positive, 181 Negative, 88 Neutral).

| Model               | Accuracy | Macro F1 |
|---------------------|----------|----------|
| Logistic Regression | 0.683    | 0.530    |
| **LinearSVC**       | **0.735**| **0.546**|

LinearSVC performs best on both metrics. The gap between accuracy and macro F1 reflects class
imbalance: the Neutral class (about 11% of reviews) is the hardest to predict, and both models
under-predict it (LinearSVC predicts only 43 Neutral reviews against 88 true ones).

## Repository structure

```
.
├── notebooks/            # main project notebook (run in Google Colab)
├── data/
│   ├── linearsvc_predictions.csv   # per-review predictions, LinearSVC
│   └── logreg_predictions.csv      # per-review predictions, Logistic Regression
├── images/model_comparison.png
├── DATASET_ATTRIBUTION.md
├── requirements.txt
└── README.md
```

Prediction files columns: `urlDrugName, condition, rating, sentiment, predicted_sentiment, correct_prediction`.

## Method
1. Convert patient ratings to sentiment labels (1-4 Negative, 5-6 Neutral, 7-10 Positive).
2. Vectorise review text with TF-IDF.
3. Train Logistic Regression and LinearSVC.
4. Compare with accuracy and macro F1 (macro F1 is used because of class imbalance).

## Reproduce
```bash
pip install -r requirements.txt
jupyter notebook notebooks/
```

## Limitations and next steps
- Labels come from star ratings, not manual annotation, so rating and review text can disagree.
- Neutral recall is weak; try class weights, resampling, or a transformer model.
- Not for clinical use.

## Data
See [DATASET_ATTRIBUTION.md](DATASET_ATTRIBUTION.md).
