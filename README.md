# Project 01 — Revenue Time Series: Noise vs Signal

This project analyses daily revenue volatility using transaction-level ecommerce data to distinguish meaningful performance changes from normal day-to-day noise.

## Dataset
Online Retail II — transaction-level data including invoice date, quantity, price, and country.

## Objective
Daily revenue fluctuates heavily. The goal is to:
- Separate signal from noise
- Avoid overreacting to single-day spikes
- Define a practical, data-driven decision rule

## Methodology
1. Clean transaction data (remove cancellations, returns, invalid rows)
2. Aggregate transactions into daily revenue
3. Smooth revenue using a 7-day rolling average
4. Measure volatility via residuals (daily revenue − rolling average)
5. Define ±2σ volatility bands using a 28-day rolling standard deviation

## Key insight
Approximately **4–5% of days** fall outside the volatility bands.  
Most daily fluctuations are consistent with normal noise rather than meaningful performance changes.

## Decision rule
Do not react to single-day movements unless revenue breaks outside the ±2σ band  
(or remains outside the band for multiple consecutive days).

## Tools
Python, pandas, NumPy, matplotlib, Jupyter Notebook

## Files
- `01_timeseries_noise_vs_signal.ipynb` — full analysis notebook
