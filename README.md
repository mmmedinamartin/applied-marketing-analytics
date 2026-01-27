# Applied Marketing Analytics

This repository contains applied data analysis projects focused on
real-world marketing and commercial decision-making.

The projects use Python, pandas, statistics, and visualisation to move from
raw transactional data to business insight.

---

## Projects

### Project 01 — Time Series: Noise vs Signal
**Objective:**  
Understand revenue dynamics by separating short-term volatility from
underlying trends.

**Key techniques:**
- Data cleaning and validation
- Daily aggregation of transactional data
- Rolling averages and smoothing
- Volatility and spike analysis

**Output:**  
`01_timeseries_noise_vs_signal.ipynb`

---

### Project 02 — Customer Cohort & Retention Analysis
**Objective:**  
Measure how customer retention evolves after first purchase and determine
whether growth is driven by acquisition or repeat behaviour.

**Key techniques:**
- Cohort assignment by first purchase month
- Cohort index construction
- Retention matrix calculation
- Heatmap visualisation

**Output:**  
`02_customer_cohort_retention.ipynb`

---

### Project 03 — Revenue Decomposition

**Objective:**
Decompose revenue into its mechanical drivers over time to understand
what must have changed for revenue to rise or fall.

Core identity:
Revenue = Active Customers × Orders per Customer × Average Order Value (AOV)

**Key techniques:**

Monthly aggregation of transaction data

Construction of revenue driver components

Structural (non-causal) interpretation of growth drivers

Lightweight visualisation for pattern comparison

**Output:**
03_revenue_decomposition.ipynb

---

## Dataset
All projects use the **Online Retail II** dataset, a real-world
transaction-level ecommerce dataset.

**Source:** Kaggle — *Online Retail II*  
**Notes:**  
- The dataset contains transactional data with customer identifiers.
- The raw CSV file is **not uploaded to GitHub** to respect licensing
  and data-sharing constraints.
- Notebooks are written so the analysis can be reproduced locally by
  downloading the dataset from Kaggle and placing it in the project folder.

This reflects standard industry practice when working with licensed or
sensitive datasets.
---

## Tools & Skills
- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- Exploratory data analysis
- Marketing analytics
- Cohort analysis
- Time-series analysis
