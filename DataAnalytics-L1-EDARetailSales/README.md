# Task 1 · EDA on Retail Sales Data
**Track:** Data Analytics — Level 1

## Objective
Perform a thorough Exploratory Data Analysis on a retail sales dataset to
uncover patterns, customer behaviour trends, and actionable business insights.

## Dataset
1,000 retail transactions with the following columns:
`Transaction ID, Date, Customer ID, Gender, Age, Product Category,
Quantity, Price per Unit, Total Amount`

## Tools & Libraries
Python, pandas, numpy, matplotlib, seaborn, Jupyter Notebook

## Analysis Performed
- Data inspection: shape, dtypes, null value check
- Descriptive statistics: mean, median, mode, standard deviation
- Date conversion and monthly / quarterly sales trend analysis
- Customer demographics: age group distribution, gender breakdown
- Product category revenue and quantity analysis
- Correlation heatmap across numerical variables
- Bonus visualization: day-of-week sales pattern

## Key Findings
- **Total Amount** correlates far more strongly with **Price per Unit**
  (r = 0.85) than with **Quantity** (r = 0.37) — high-value purchases are
  driven more by premium items than bulk buying.
- Customers aged **26–60** generate ~73% of total revenue.
- **Saturday** is the strongest sales day, both in total revenue (₹78,815)
  and average transaction value (₹525).
- **Q4 2023** was the strongest quarter (₹1,26,190 in revenue).
- Revenue is nearly balanced across Electronics, Clothing, and Beauty
  categories, though Electronics earns more per unit sold.

## Business Recommendations
1. Focus promotional campaigns around Saturdays and Q4 (holiday season),
   which show the highest revenue concentration.
2. Prioritize marketing spend on the 26–60 age segment, which drives the
   majority of revenue; the 60+ segment is comparatively under-penetrated.
3. Drive revenue growth through upselling to higher-value/premium products
   rather than promoting bulk-quantity purchases, since price per unit has
   a much stronger relationship with total spend than quantity does.

## Files in This Folder
- `TASK_1_-_EDA_on_Retail_Sales_Data.ipynb` — full analysis notebook
- `retail_sales_dataset.csv` — source dataset

## Author
Shriya Torgale