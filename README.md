#Customer Revenue Risk & Predictive Retention Modeling

## Executive Summary

This project quantifies revenue concentration risk and translates predictive churn modeling into financial impact. 
With Top 10% customers generating 63.9% of total revenue (Gini = 0.74), and a churn model achieving AUC = 0.78, 
approximately $13.0M in revenue exposure was identified among high-value customers.

## Project Overview

This project analyzes revenue concentration, retention structure, and churn risk within an e-commerce dataset (Online Retail II, UCI).

The objective is to assess whether revenue is sustainably diversified or structurally dependent on a small high-value segment — and to quantify revenue exposure using predictive modeling.


## Dataset

- ~500,000 transaction records  
- Fields: InvoiceDate, Customer ID, Quantity, Price  
- Platform: Google BigQuery  

Revenue calculated as:

```
revenue = Quantity × Price
```


## Revenue Concentration Analysis
 
 Key Findings

- **Top 10% of customers generate 63.9% of total revenue**
- **Gini coefficient: 0.74** → high revenue inequality
- **HHI: 0.0042** → meaningful concentration despite large customer base

 Interpretation

Revenue is structurally dependent on a small VIP segment.  
Loss of high-value customers could materially increase revenue volatility.



 RFM Customer Segmentation

| Segment | Customers | Description |
|----------|-----------|-------------|
| Champions | 1,309 | High frequency & high value |
| Loyal | 1,041 | Stable repeat buyers |
| New Customers | 345 | Recently acquired |
| At Risk (High Value) | 151 | Declining valuable customers |
| Others | 3,032 | Low activity |

Key insight:

A small high-value segment disproportionately drives revenue.



 Cohort Retention Analysis

![Cohort Retention Heatmap](cohort_heatmap.png)

 Retention Metrics

- Average Month-1 retention: ~22%
- Average Month-3 retention: ~18%
- 4pp decline (~18% relative drop)

 Interpretation

Retention stabilizes around 15–25%, indicating sustainable but non-compounding customer persistence.



Predictive Churn Modeling (90-Day Definition)

Churn Definition

A customer is labeled as churned if no purchase occurs within 90 days after their last transaction.

Model

- Logistic Regression (BigQuery ML)
- AUC: **0.78**
- Features: frequency, monetary, tenure, avg order value, purchase interval

The initial model achieved AUC = 1.0 due to feature leakage caused by overlap between recency-based features and churn definition.



Revenue Risk Simulation

Using predicted churn probabilities:

- **High-value & high-risk customers identified: 1,056**
- **Revenue at risk: $13.0M**

This framework enables data-driven prioritization of retention efforts based on quantified financial exposure.

Business Interpretation

Targeted retention efforts on this segment could significantly reduce revenue volatility.

If churn probability is reduced by just 10% within this group, approximately:

> ~$1.3M in revenue could potentially be preserved.



Business Implications

1. Revenue concentration risk exists (VIP dependency).
2. Predictive modeling enables proactive retention.
3. High-risk high-value customers should receive targeted incentives.
4. Retention improvements directly translate into measurable revenue impact.

This analysis demonstrates the ability to move from structured SQL-based analytics to predictive modeling within a data warehouse environment.

Tools Used

- Google BigQuery
- BigQuery ML
- Window Functions (NTILE, LAG)
- SAFE_DIVIDE
- Cohort Analysis
- Logistic Regression



Project Outcome

This project transitions from descriptive analytics to predictive revenue risk management, integrating:

- Revenue inequality measurement
- Behavioral segmentation
- Cohort retention tracking
- Machine learning churn prediction
- Financial exposure estimation
	

