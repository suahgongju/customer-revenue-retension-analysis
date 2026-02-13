# Customer Revenue Concentration & Retention Analysis

## 📌 Project Overview
This project analyzes revenue concentration and customer retention structure within an e-commerce dataset.

The goal is to understand:
- How revenue is distributed across customers
- The level of customer dependency
- Repeat purchase behavior
- Monthly revenue growth patterns

---

## 📊 Dataset
Online Retail II (UCI)  
~500K transaction records  
Fields: InvoiceDate, Customer ID, Quantity, Price

---

## 🔍 Analysis Performed

### 1️⃣ Customer Lifetime Value (LTV)
- Calculated total revenue per customer
- Highest LTV exceeded $608K

### 2️⃣ Revenue Concentration (Pareto Analysis)
- Used SQL NTILE window function
- Top 10% customers (589 users) generated ~64% of total revenue

### 3️⃣ Repeat Purchase Rate
- 72% of customers made repeat purchases
- Indicates strong customer retention structure

### 4️⃣ Month-over-Month Growth
- Detected 50% revenue surge in March 2010
- Suggests potential seasonal or promotional impact

---

## 💡 Business Implications
- Revenue heavily depends on VIP segment
- Strong opportunity for targeted retention strategy
- Further analysis recommended on high-growth months

---

## 🛠 Tools Used
- SQL (BigQuery)
- Window Functions (NTILE, LAG)
- Aggregation & Segmentation Analysis
