Customer Segmentation using RFM Analysis
Overview

This project performs Customer Segmentation using RFM (Recency, Frequency, Monetary) Analysis on a real-world e-commerce dataset.
The goal is to identify high-value customers, churn risk segments, and growth opportunities through data analysis, cohort behavior, and business intelligence visualization.

Business Problem

Companies often struggle to:

Identify their most valuable customers

Detect churn risk early

Optimize marketing & retention strategy

Increase Customer Lifetime Value (CLV)

This project solves these using data-driven segmentation.

Dataset

Online Retail dataset (UK e-commerce transactions)

~397K transactions

4K+ customers

Period: Dec 2010 – Dec 2011

Methodology

1. Data Cleaning

Removed cancellations & invalid transactions

Handled missing Customer IDs

Created Revenue metric

2. RFM Calculation

Recency → Days since last purchase

Frequency → Number of purchases

Monetary → Total revenue per customer

3. Customer Segmentation
Customers classified into:

Champions

Loyal Customers

At Risk

Hibernating

Returning Customers

4. BI Dashboard (Tableau)
Interactive dashboard including:

Segment Distribution

Revenue by Segment

Recency vs Monetary Behavior

Key Insights

Champions & Loyal Customers drive most revenue

Large portion of customers are Hibernating → churn risk

Customers with high Recency & low Frequency require re-engagement

Revenue retention is highly dependent on repeat buyers

Tools & Technologies

Python (Pandas, NumPy, Matplotlib, Seaborn)

Tableau Public (Dashboard & Visualization)

Jupyter / Google Colab

GitHub (Portfolio & Version Control)

Project Structure
customer-segmentation-rfm/
│
├── rfm_dashboard.twbx
├── rfm_segments.csv
├── rfm_segmentation.ipynb
├── Online Retail.xlsx
└── README.md

Business Value

Customer Retention Strategy

Churn Detection

Marketing Targeting

Revenue Optimization

CLV Growth
