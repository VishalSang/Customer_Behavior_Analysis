# Customer Shopping Behavior Analysis

**Tools:** Python · PostgreSQL · Power BI · Git

An end-to-end retail analytics project that explores customer purchasing patterns, segments shoppers by behavior and surfaces actionable business recommendations for pricing, promotions and retention strategy.

---

## Overview

This project analyses 3,900 retail transactions across 18 features to answer three core business questions:

- Which customer segments drive the most revenue?
- Which products are dependent on discounts to sell?
- What does the customer loyalty breakdown look like across the business?

The analysis runs from raw data ingestion through SQL querying, exploratory data analysis, data cleaning and a final Power BI dashboard built for stakeholder self-service.

---

## Dataset

| Property | Detail |
|---|---|
| Records | 3,900 transactions |
| Features | 18 (customer demographics, product category, purchase amount, discount, subscription status, shipping type, review rating) |
| Source | Retail customer transactions dataset |
| Format | CSV |

---

## Tools

| Tool | Purpose |
|---|---|
| Python (Pandas, NumPy) | Data loading, EDA, cleaning and feature engineering |
| PostgreSQL | SQL querying for business insight extraction |
| Power BI | Interactive dashboard and visualisation |
| Git | Version control for all scripts and queries |
| PowerPoint | Executive summary presentation |

---

## Steps

### 1. Data Loading and Exploration
- Loaded the dataset into a Pandas DataFrame
- Inspected column types, null values and basic statistics
- Identified skewed distributions, outliers and inconsistencies

### 2. Data Cleaning
- Imputed missing values using category median
- Standardised column naming and data types
- Removed duplicate records and inactive entries
- Validated data integrity before loading to the database

### 3. Feature Engineering
- Created age group buckets (e.g. 18-25, 26-35, 36-50, 50+)
- Derived purchase frequency per customer
- Built a customer loyalty tier field (New, Returning, Loyal) based on purchase history

### 4. SQL Analysis
Loaded the cleaned dataset into PostgreSQL and wrote 10+ queries to answer business questions. Key queries covered:

- Revenue by customer segment and gender
- Discount dependency by product category
- Loyalty tier distribution and average spend
- Revenue breakdown by subscription status and shipping type

All queries use CTEs and joins and are saved in `/queries`.

### 5. Power BI Dashboard
Built an interactive 3-page dashboard with cross-filtering across:

- Subscription status
- Gender
- Product category
- Shipping type
- Loyalty tier

Designed for stakeholder self-service — no SQL knowledge required to explore the data.

### 6. Report and Presentation
- Written report summarising methodology, findings and recommendations
- PowerPoint presentation with executive-level summary for non-technical stakeholders

---

## Dashboard

The Power BI dashboard covers three views:

**Page 1 — Revenue Overview**
Total revenue, transactions, average order value and top-performing product categories.

**Page 2 — Customer Segmentation**
Revenue split by gender, age group, loyalty tier and subscription status.

**Page 3 — Pricing and Discount Analysis**
Products with high discount dependency, discount rate vs. revenue correlation and promotional effectiveness by category.

---

## Results

Five business recommendations delivered from the analysis:

1. **Male shoppers drove approximately 68% of total revenue** — marketing and product mix should reflect this while identifying opportunities to grow the female segment.

2. **Five products relied on discounts for roughly 50% of their sales volume** — these items need pricing strategy review to reduce margin erosion.

3. **Loyal customers had a significantly higher average order value** than new or returning customers — a loyalty rewards programme could accelerate tier progression.

4. **Subscription customers outspent non-subscribers across every category** — subscription growth should be a priority channel.

5. **Standard shipping was the dominant choice** but express shipping correlated with higher-value orders — a targeted upsell prompt at checkout could increase revenue per transaction.

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn psycopg2-binary sqlalchemy
```

**3. Run the Python analysis**
```bash
jupyter notebook notebooks/eda_and_cleaning.ipynb
```

**4. Set up PostgreSQL**

Create a database and run the setup script:
```bash
psql -U your_username -d your_database -f sql/create_tables.sql
psql -U your_username -d your_database -f sql/load_data.sql
```

**5. Run SQL queries**
```bash
psql -U your_username -d your_database -f queries/revenue_by_segment.sql
```

**6. Open the dashboard**

Open `dashboard/Customer_Shopping_Analysis.pbix` in Power BI Desktop.

---

## Repository Structure

```
customer-shopping-behavior-analysis/
│
├── data/
│   └── shopping_behavior.csv
│
├── notebooks/
│   └── eda_and_cleaning.ipynb
│
├── sql/
│   ├── create_tables.sql
│   └── load_data.sql
│
├── queries/
│   ├── revenue_by_segment.sql
│   ├── discount_dependency.sql
│   ├── loyalty_tier_analysis.sql
│   └── subscription_revenue.sql
│
├── dashboard/
│   └── Customer_Shopping_Analysis.pbix
│
├── report/
│   └── Customer_Shopping_Analysis_Report.pdf
│
├── presentation/
│   └── Customer_Shopping_Analysis.pptx
│
└── README.md
```

---

## Contact

**Vishal Sang**
vishalsang43@gmail.com · [LinkedIn](https://www.linkedin.com/in/vishal-sang) · Toronto, ON
