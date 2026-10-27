# Dataset Attribution

The reviews analysed in this project come from the **Drug Review Dataset (Druglib.com)**,
published in the UCI Machine Learning Repository.

- **Source:** https://archive.ics.uci.edu/dataset/461/drug+review+dataset+druglib+com
- **Original authors:** Surya Kallumadi and Felix Gräßer
- **Associated paper:** Gräßer, F., Kallumadi, S., Malberg, H., & Zaunseder, S. (2018).
  *Aspect-Based Sentiment Analysis of Drug Reviews Applying Cross-Domain and Cross-Data Learning.*
  Proceedings of the 2018 International Conference on Digital Health (DH '18), ACM.
- **License:** CC BY 4.0 (per the UCI repository listing; please verify on the source page)

This repository does **not** redistribute the raw review text. The files in `data/` contain only
drug name, condition, rating, and sentiment labels/predictions (829 rows each).

## Label construction
Sentiment labels were derived from the numeric patient rating:

| Rating | Sentiment |
|--------|-----------|
| 1-4    | Negative  |
| 5-6    | Neutral   |
| 7-10   | Positive  |
