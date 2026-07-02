# Olist E-Commerce: Order Fulfilment & Customer Satisfaction

The Olist Brazilian E-Commerce dataset spans 100,000+ orders placed between 2016 and 2018 across the biggest online department store 
marketplace in Brazil. This project investigates a deceptively simple question: does delivery performance actually drive customer satisfaction, 
or is it something else entirely?

The answer, it turns out, is specific. It's not how long delivery takes, but whether the order arrived when it was promised.

## Objective

Perform end-to-end exploratory data analysis across four merged datasets to understand what drives review scores, with a focus on delivery timing, 
delay behaviour, and payment patterns.

## Key Findings

- **Late deliveries are the strongest predictor of low review scores.**  
  Orders that arrived after the estimated date averaged a review score of  2.3, compared to 4.2 for on-time orders — a gap that held consistently 
  across all product categories.

- **Delay days matter more than delivery days.**  
  The Spearman correlation between `is_late` and `review_score` was –0.31,   stronger than the correlation with raw `delivery_days` (–0.23). 

- **Payment method has almost no effect on satisfaction.**  
  Average review scores across credit card, debit card, boleto, and voucher payments were nearly identical.

- **Delivery times are right-skewed.**  
  Most orders arrived within a reasonable window, but a long tail of   delayed orders pulled the average up significantly.

## Analysis Pipeline

1. Load and merge 4 datasets (orders, reviews, payments, customers)
2. Parse datetime columns and engineer `delivery_days`, `delay_days`, `is_late`
3. Handle missing values and remove outliers via IQR method
4. Univariate analysis — review score distribution, delivery day histogram
5. Bivariate analysis — box plots by review score, on-time vs late comparison
6. Spearman correlation matrix and heatmap

## Dataset

[Olist Brazilian E-Commerce Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) — Kaggle

| File | Description |
|------|-------------|
| `olist_orders_dataset.csv` | Order lifecycle — purchase, delivery, estimated dates |
| `olist_order_reviews_dataset.csv` | Customer review scores (1–5) |
| `olist_order_payments_dataset.csv` | Payment method and total value |
| `olist_customers_dataset.csv` | Customer state/location |

## Stack

`Python` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `scipy`


*VAC Project · B.Tech AI & DS· JEMTEC, GGSIPU · 2026*