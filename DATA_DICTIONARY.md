# Marketing Ad Spend Dataset - Data Dictionary

## Overview
- **Rows:** 365 (daily data for full year 2023)
- **Use case:** A4 exercise on relationships and confounding
- **File:** marketing_ad_spend_data.csv

---

## Column Descriptions

| Column | Type | Description |
|--------|------|-------------|
| `date` | date | Calendar date (2023-01-01 to 2023-12-31) |
| `day_of_week` | int | Day of week (0=Monday, 6=Sunday) |
| `is_weekend` | int | Weekend flag (1=Saturday/Sunday, 0=weekday) |
| `google_ads_spend` | float | Daily spend on Google Ads ($) |
| `facebook_ads_spend` | float | Daily spend on Facebook Ads ($) |
| `email_spend` | float | Daily spend on Email marketing ($) |
| `total_ad_spend` | float | Sum of all ad spend ($) |
| `revenue` | float | Daily revenue ($) |
| `transactions` | int | Number of transactions/orders |
| `avg_order_value` | float | Average order value (revenue ÷ transactions) |

---

## Built-in Relationships (for A4 exploration)

### ✅ Relationship 1: **Ad Spend vs Revenue**
**Naïve view:** "Ad spend and revenue move together — ads must be driving revenue!"

**Reality:** Both are driven by **seasonality**
- Companies increase ad budgets in Q4 (Nov-Dec)
- Revenue naturally spikes in Q4 due to holiday shopping
- **Confounder:** Seasonality affects both variables

**A4 exercise:** 
1. Plot `total_ad_spend` vs `revenue` (scatter) — you'll see positive correlation
2. Plot both over time — you'll see they spike together in Q4
3. Control for month (e.g., plot within-month relationship) — correlation weakens

---

### ✅ Relationship 2: **Transactions vs Revenue**
**Naïve view:** "More transactions = more revenue" (obvious, mechanical)

**Reality:** True, but AOV also varies
- Weekends have fewer transactions but higher AOV (fewer, bigger orders)
- **Confounder:** Day of week affects both

**A4 exercise:**
1. Plot `transactions` vs `revenue` — strong positive correlation
2. Color points by `is_weekend` — weekend points cluster differently
3. Show that the relationship isn't purely linear due to AOV variation

---

### ✅ Relationship 3: **Email Spend vs Revenue**
**Naïve view:** "Email spend correlates with revenue on Fridays"

**Reality:** Email campaigns launch on Fridays, revenue is naturally higher on weekdays
- **Confounder:** Day of week (Fridays have email boosts AND are high-revenue days)

**A4 exercise:**
1. Plot `email_spend` vs `revenue`
2. Show that Friday points have high spend AND high revenue
3. Within-weekday analysis shows weaker relationship

---

## True Causal Structure (hidden in the data)

For context (don't peek until after your analysis!):

**Revenue is driven by:**
1. **Base demand** (~70% of revenue)
   - Seasonality (Q4 spike)
   - Day-of-week patterns (lower on weekends)

2. **Ad spend** (~25% of revenue)
   - Google Ads: $2 revenue per $1 spent
   - Facebook Ads: $1.50 revenue per $1 spent
   - Email: $1 revenue per $1 spent

3. **Random noise** (~5%)

**Ad spend is driven by:**
- Seasonality (companies budget more in Q4)
- Email: Friday boost (campaigns)

**The confounding:**
- Ad spend and revenue both increase in Q4
- This creates a spurious correlation beyond the true causal effect
- Naïve analysis would overestimate ad effectiveness

---

## Suggested A4 Workflow

### Step 1: Explore naïve relationships
- Scatter plot: `total_ad_spend` vs `revenue`
- Calculate correlation
- **Question:** Does ad spend drive revenue?

### Step 2: Introduce time
- Line plot: both variables over time
- Observation: Both spike in Nov-Dec
- **Question:** Is this causation or confounding?

### Step 3: Control for seasonality
- Option A: Plot within-month relationships (facet by month)
- Option B: De-trend both variables (subtract monthly averages)
- **Result:** Correlation weakens — seasonality was inflating it

### Step 4: Explore other confounders
- Day-of-week effects
- Email spend on Fridays
- Weekend patterns

### Step 5: Document findings
- "Here's what I thought (naïve correlation)"
- "Here's what I learned (confounding by seasonality)"
- "What would be needed to establish causation" (experiment, natural experiment, better controls)

---

## Key Takeaways for A4

1. **Correlation ≠ causation** (even when there IS a true causal effect)
2. **Seasonality** is the most common confounder in business data
3. **Always plot over time** before trusting a scatter plot
4. **Control for confounders** (stratify, de-trend, model) before interpreting relationships

---

## Next Steps After A4

Once you've completed A4 with this dataset, you'll be ready for:
- **A5:** Build regression-ready features (lags, rolling averages)
- **A6:** Fit a controlled regression model with appropriate humility

This dataset will work for all three exercises (A4, A5, A6).

---

**Questions?** Load the data and start with a simple scatter plot of `total_ad_spend` vs `revenue`. See what story it tells before you interrogate it.
