# Applied Marketing Analytics

This repository contains applied data analysis projects focused on real-world marketing and commercial decision-making.

The projects use Python, pandas, statistics, and visualisation to move from raw transactional data to business insight.

---

## Projects

### Project 01 — Time Series: Noise vs Signal
**Objective:** Understand revenue dynamics by separating short-term volatility from underlying trends.

**Key techniques:**
* Data cleaning and validation
* Daily aggregation of transactional data
* Rolling averages and smoothing
* Volatility and spike analysis

**Dataset:** Online Retail II (ecommerce transaction data)

**Output:** `01_timeseries_noise_vs_signal.ipynb`

---

### Project 02 — Customer Cohort & Retention Analysis
**Objective:** Measure how customer retention evolves after first purchase and determine whether growth is driven by acquisition or repeat behaviour.

**Key techniques:**
* Cohort assignment by first purchase month
* Cohort index construction
* Retention matrix calculation
* Heatmap visualisation

**Dataset:** Online Retail II (ecommerce transaction data)

**Output:** `02_customer_cohort_retention.ipynb`

---

### Project 03 — Revenue Decomposition
**Objective:** Decompose revenue into its mechanical drivers over time to understand what must have changed for revenue to rise or fall.

**Core identity:** Revenue = Active Customers × Orders per Customer × Average Order Value (AOV)

**Key techniques:**
* Monthly aggregation of transaction data
* Construction of revenue driver components
* Structural (non-causal) interpretation of growth drivers
* Lightweight visualisation for pattern comparison

**Dataset:** Online Retail II (ecommerce transaction data)

**Output:** `03_revenue_decomposition.ipynb`

---

### Project 04 — Relationships & Confounding
**Objective:** Learn to identify spurious correlations and distinguish correlation from causation before building predictive models.

**Key techniques:**
* Scatter plot analysis
* Correlation measurement
* Confounding variable identification
* Seasonality effects on correlations
* Controlled comparison (within-group correlation)
* Non-linear relationship detection

**Key findings:**
* Seasonality inflated ad spend-revenue correlation by 40.7%
* Transaction-revenue relationship reverses at high volumes
* Day-of-week patterns don't always create spurious correlations

**Dataset:** Marketing Ad Spend Data (synthetic dataset designed for confounding analysis)

**Output:** `04_relationships_confounding.ipynb`

---

## Datasets

### Online Retail II (Projects 01-03)
**Source:** [Kaggle — Online Retail II](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci)

**Description:** Real-world ecommerce transaction-level dataset containing customer identifiers, purchase dates, and order details.

**Notes:**
* The raw CSV file is not uploaded to GitHub to respect licensing and data-sharing constraints
* Notebooks are written so the analysis can be reproduced locally by downloading the dataset from Kaggle and placing it in the project folder
* This reflects standard industry practice when working with licensed or sensitive datasets

### Marketing Ad Spend Data (Project 04)
**Source:** Synthetic data generated for educational purposes

**Description:** 365 days of daily marketing spend (Google Ads, Facebook Ads, Email) and revenue data for 2023, designed with built-in confounding factors (seasonality, day-of-week effects).

**Notes:**
* Specifically created to demonstrate correlation vs causation concepts
* Includes realistic confounding patterns found in real marketing analytics
* Dataset and data dictionary included in repository

---

## Tools & Skills

**Technical:**
* Python
* pandas
* NumPy
* Matplotlib
* Seaborn

**Analytical:**
* Exploratory data analysis
* Marketing analytics
* Cohort analysis
* Time-series analysis
* Correlation analysis
* Confounding identification
* Statistical interpretation
