# 📊 Customer Segmentation using RFM Analysis

## 🧠 Project Overview
This project performs **Customer Segmentation using RFM (Recency, Frequency, Monetary) Analysis** on a real-world e-commerce dataset (~397K transactions).

The goal is to:
- Identify high-value customers
- Detect churn risk segments
- Improve retention strategy
- Optimize Customer Lifetime Value (CLV)

The project combines **Python analytics + Tableau BI dashboard** for full business insight.

---

## 💼 Business Problem
Companies often struggle to:

- Identify their most valuable customers  
- Detect churn early  
- Optimize marketing & retention strategy  
- Increase Customer Lifetime Value (CLV)  

This project solves these challenges using **data-driven customer segmentation**.

---

## 📦 Dataset
**Online Retail Dataset (UK E-commerce)**

- ~397K transactions  
- 4K+ customers  
- Period: Dec 2010 – Dec 2011  

---

## ⚙️ Methodology

### 1. Data Cleaning
- Removed cancellations & invalid transactions  
- Handled missing Customer IDs  
- Created Revenue metric  

### 2. RFM Calculation
- **Recency** → Days since last purchase  
- **Frequency** → Number of purchases  
- **Monetary** → Total revenue per customer  

### 3. Customer Segmentation
Customers classified into:

- 🏆 Champions  
- 💎 Loyal Customers  
- ⚠️ At Risk  
- 😴 Hibernating  
- 🔁 Returning Customers  

### 4. BI Dashboard (Tableau)
Interactive dashboard includes:

- Segment Distribution  
- Revenue by Segment  
- Recency vs Monetary Behavior  

---

## 📊 Key Insights

- Champions & Loyal Customers generate **majority of revenue**
- Large portion of customers are **Hibernating → churn risk**
- Customers with **high Recency & low Frequency need re-engagement**
- Revenue retention depends strongly on **repeat customers**

---

## 🛠 Tools & Technologies

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Tableau Public (Dashboard & Visualization)
- Jupyter / Google Colab
- GitHub (Portfolio & Version Control)

---

## 💡 Business Value

- Customer Retention Strategy  
- Churn Detection  
- Marketing Targeting  
- Revenue Optimization  
- CLV Growth  

---

End-to-End Data Pipeline Architecture

This project follows a complete analytics pipeline from raw transactional data to business intelligence dashboard.


Raw Data (Excel / Transactions)
        │
        ▼
Data Cleaning & Validation (Python / Pandas)
- Remove null CustomerID
- Remove cancellations / negative quantity
- Handle missing values
        │
        ▼
Feature Engineering
- Revenue calculation
- Invoice Month extraction
- Cohort Month
- RFM Metrics (Recency, Frequency, Monetary)
        │
        ▼
Customer Segmentation Logic
- RFM Scoring
- Segment mapping (Champions, Loyal, At Risk, Hibernating)
        │
        ▼
Analytics Data Mart (CSV outputs)
- cohort_retention.csv
- revenue_retention.csv
- rfm_segments.csv
        │
        ▼
Business Intelligence Layer (Tableau)
- Cohort Retention Heatmap
- Revenue Retention
- Customer Segments Dashboard
- Revenue & Behavior Analysis

---

Data Engineering / SQL Equivalent (Production Style)

Although this project was implemented in Python, below is how the same transformation would typically run in a data warehouse (Snowflake / BigQuery / SQL Server).


RFM Metrics (SQL)

SELECT
    CustomerID,
    DATEDIFF(day, MAX(InvoiceDate), '2011-12-31') AS Recency,
    COUNT(DISTINCT InvoiceNo) AS Frequency,
    SUM(Quantity * UnitPrice) AS Monetary
FROM transactions
WHERE Quantity > 0
  AND CustomerID IS NOT NULL
GROUP BY CustomerID;

---

Cohort Assignment (SQL)

SELECT
    CustomerID,
    MIN(DATE_TRUNC('month', InvoiceDate)) AS CohortMonth
FROM transactions
GROUP BY CustomerID;

---

Retention Matrix (SQL logic concept)

SELECT
    CohortMonth,
    InvoiceMonth,
    COUNT(DISTINCT CustomerID) AS ActiveCustomers
FROM cohort_table
GROUP BY CohortMonth, InvoiceMonth;

---

Business Intelligence Layer

The Tableau dashboard transforms analytics into decision-making insights.

Key Business Questions Answered

Which customer cohorts retain best over time?

How fast do customers churn after first purchase?

Which segments generate most revenue?

Where should marketing focus: retention vs acquisition?

Which customers are at churn risk?

Business Insights
Customer Retention

Early cohorts show strong long-term retention

Newer cohorts drop faster → possible acquisition quality issue

Revenue Behavior

Revenue retention remains stronger than user retention → high-value repeat buyers

Some cohorts increase value over time (customer maturation)

Customer Segmentation

Champions & Loyal Customers drive majority of revenue

Large Hibernating segment = reactivation opportunity

At Risk segment → churn prevention target

Business Impact

This analysis enables:

Targeted retention campaigns

High-value customer prioritization

Churn prediction strategy

Customer Lifetime Value optimization

Marketing ROI improvement

Tech Stack

Python (Pandas, NumPy, Matplotlib, Seaborn)

Cohort & Retention Analysis

RFM Segmentation

Tableau Dashboard

Data Pipeline Design

SQL (Analytical equivalent)
