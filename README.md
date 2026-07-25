# Customer Segmentation

Unsupervised clustering of a grocery firm's customer database to identify distinct customer segments for targeted marketing.

## Overview

Customer segmentation groups customers by shared characteristics so a business can tailor products, offers, and messaging to each group's needs. This project applies clustering to demographic, spending, and purchase-channel data to uncover four actionable customer segments.

## Dataset

`marketing_campaign.csv` — tab-separated file containing customer demographics (income, birth year, education, marital status, household composition), spending across product categories (wines, fruits, meat, fish, sweets, gold), purchase channels (web, catalog, store), campaign response history, and enrollment date. Place this file in the same directory as the notebook before running it.

## Approach

1. **Data cleaning** — drop rows with missing income, convert enrollment date to datetime, remove age/income outliers.
2. **Feature engineering** — derive `Age`, `Spent` (total spend across categories), `Customer_For` (tenure), `Living_With`, `Children`, `Family_Size`, `Is_Parent`, and simplified `Education` tiers.
3. **Preprocessing** — label-encode categorical features and scale all features with `StandardScaler`.
4. **Dimensionality reduction** — reduce features to 3 components with PCA.
5. **Clustering** — determine the optimal number of clusters via the Elbow method and silhouette analysis (k=4), then cluster with both K-Means and Agglomerative (hierarchical) clustering for comparison.
6. **Evaluation & profiling** — visualize clusters in 3D, compare income/spending/deal/campaign patterns across clusters, and profile each segment by demographics.

## Results

Both clustering methods converge on four comparable segments:

| Segment | Profile |
|---|---|
| Affluent Couples, No or Few Kids | High income, high spending, premium-focused |
| Young Single-Child Families | Lower income, price-sensitive, essential purchases |
| Average-Income Parents | Moderate income and spending, value/quality balance |
| Older Low-Income Families with Teens | Lower income, larger households, budget-focused |

Each segment comes with a suggested marketing strategy (product focus, promotion type, and channel) detailed in the notebook's concluding section.

## Requirements

- Python 3
- pandas, numpy
- scikit-learn
- scipy
- matplotlib, seaborn
- yellowbrick (installed automatically in the first cell via `pip install yellowbrick`)

Install manually if needed:

```bash
pip install pandas numpy scikit-learn scipy matplotlib seaborn yellowbrick
```

## Usage

1. Clone the repo and ensure `marketing_campaign.csv` is present alongside the notebook.
2. Open `Customer_Segmentation_Project.ipynb` in Jupyter Notebook / JupyterLab.
3. Run all cells top to bottom.

## Project Structure

```
.
├── Customer_Segmentation_Project.ipynb   # Main analysis notebook
├── marketing_campaign.csv                # Dataset (not included — add your own)
└── README.md
```

## License

Add a license of your choice (e.g. MIT) if you plan to share this publicly.
