# 📊 Customer Segmentation & Cohort Retention Analytics  
**End-to-End Data Analytics Project | Python · SQL · Tableau · BI**

---

## 🧭 Executive Summary

This project builds a complete **end-to-end analytics pipeline** to analyze **customer behavior, retention, and revenue performance** using a real-world UK e-commerce dataset.

It identifies:

- 💎 High-value customer segments  
- ⚠️ Churn risk customers  
- 📉 Retention & cohort behavior  
- 💰 Revenue sustainability  

All insights are delivered via an **interactive Tableau dashboard** for business decision-making.

---

## 🎯 Business Problem

Companies often struggle to:

- Identify their most valuable customers  
- Detect churn early  
- Improve retention & marketing ROI  
- Increase Customer Lifetime Value (CLV)  
- Understand long-term cohort behavior  

This project solves these challenges using **data-driven segmentation and retention analytics**.

---

## ⚙️ End-to-End Data Pipeline

Raw Transactions → Data Cleaning → Feature Engineering → RFM Segmentation → Cohort Analytics → BI Dashboard


### 🔹 Data Preparation
- Remove cancellations / negative quantity  
- Remove missing CustomerID  
- Clean revenue & timestamps  

### 🔹 Feature Engineering
- Revenue calculation  
- Invoice Month  
- Cohort Month  
- RFM Metrics  

### 🔹 Analytics Layer
- Customer Segmentation (RFM)  
- Cohort Retention  
- Revenue Retention  

### 🔹 BI Layer
- Tableau Dashboard  
- Retention Heatmap  
- Segment Analysis  

---

## 🧠 SQL Equivalent (Production Thinking)

Although implemented in Python, below shows **how this would run in a data warehouse**.

### RFM Metrics

```sql
SELECT
    CustomerID,
    DATEDIFF(day, MAX(InvoiceDate), '2011-12-31') AS Recency,
    COUNT(DISTINCT InvoiceNo) AS Frequency,
    SUM(Quantity * UnitPrice) AS Monetary
FROM transactions
WHERE Quantity > 0
  AND CustomerID IS NOT NULL
GROUP BY CustomerID;


Cohort Assignment

SELECT
    CustomerID,
    MIN(DATE_TRUNC('month', InvoiceDate)) AS CohortMonth
FROM transactions
GROUP BY CustomerID;

---

## 📊 Business Intelligence (Tableau)
The dashboard answers key business questions:
Which cohorts retain customers best?
How fast do customers churn?
Which segments generate most revenue?
Where should marketing focus?
Which customers are at risk?


🔎 Key Insights
👥 Customer Retention
Early cohorts show stronger long-term retention
Newer cohorts drop faster → possible acquisition quality issue


💰 Revenue Behavior
Revenue retention stronger than customer retention
Some cohorts increase value over time


🧩 Customer Segmentation
Champions & Loyal Customers drive most revenue
Large Hibernating segment = reactivation opportunity
At Risk segment requires churn prevention


🚀 Business Impact
This analysis enables:
Targeted retention campaigns
Churn prevention strategy
Marketing optimization
CLV improvement
Revenue growth insights


🗂 Dataset
Online Retail Dataset (UK E-commerce)
~397K transactions
4K+ customers
Period: Dec 2010 – Dec 2011


🛠 Tech Stack
Python (Pandas, NumPy, Matplotlib, Seaborn)
Cohort & Retention Analysis
RFM Segmentation
Tableau Dashboard
SQL (Analytical equivalent)
Data Pipeline Design
