# Task 2 · Customer Segmentation Analysis

## Objective
Apply clustering algorithms to segment an e-commerce company's customer base into distinct groups based on purchasing behaviour, enabling targeted marketing strategies.

## Tech Stack
- Python
- pandas, numpy
- scikit-learn (StandardScaler, KMeans)
- matplotlib, seaborn
- Jupyter Notebook

## Dataset
A trimmed subset of the UCI "Marketing Campaign" dataset (2,240 customers), containing demographic and wine-purchase behaviour fields:
`ID`, `Year_Birth`, `Education`, `Marital_Status`, `Income`, `Kidhome`, `Teenhome`, `Dt_Customer`, `Recency`, `MntWines`.

> Note: This subset does not include purchase-count columns (web/store/catalog purchases), so classic RFM (Recency, Frequency, Monetary) could not be built as-is. See *Approach* below for how this was handled.

## Approach
1. **Data cleaning** — handled missing `Income` values (IQR-based outlier check + mean imputation), converted `Dt_Customer` to datetime, checked for duplicate customers, and engineered `Family_size` / `Has_children` from `Kidhome`/`Teenhome`/`Marital_Status`.
2. **Descriptive statistics** — average wine spend and average customer tenure.
3. **Feature selection** — since true purchase-frequency data wasn't available, `Income` was used as a spending-capacity proxy alongside `Recency` and `MntWines` (Monetary, wine-scoped). This is referred to as an **Income–Recency–Monetary (wine) segmentation** rather than classic RFM.
4. **Standardisation** — features scaled with `StandardScaler` before clustering, since K-Means relies on Euclidean distance.
5. **Clustering** — K-Means applied with the optimal number of clusters (K=3) chosen via the Elbow Method.
6. **Visualisation** — scatter plots of Income vs. Wine Spend and Recency vs. Wine Spend, coloured by cluster; bar chart of customer count per cluster.
7. **Cluster profiling** — mean feature values calculated per cluster to characterise each customer segment.

## Segments & Marketing Recommendations
| Cluster | Profile | Suggested Action |
|---|---|---|
| High Spenders (Active VIPs) | High income, low recency, high wine spend | Loyalty rewards, early access to premium/limited releases |
| At-Risk VIPs | High income, high recency, moderate-high wine spend | Win-back campaigns, personalised re-engagement offers |
| Budget Shoppers | Lower income, variable recency, low wine spend | Value bundles, discount-led promotions, entry-level offers |

## Files
- `TASK_2_-_Customer_Segmentation_Analysis.ipynb` — full analysis notebook
- `retail_sales_dataset.csv` / dataset file — source data (or link to Kaggle/UCI source if not included)

## How to Run
1. Open the notebook in Jupyter or Google Colab.
2. Ensure the dataset CSV is in the same directory (or update the file path in the first code cell).
3. Run all cells top to bottom.
