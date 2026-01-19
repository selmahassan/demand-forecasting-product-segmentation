# Demand Forecasting & Product Segmentation

## Overview
This project builds an end-to-end **weekly product-level demand forecasting system** using historical sales and pricing data. The analysis combines **time series feature engineering**, **unsupervised product segmentation (K-Means Clustering)**, and a **gradient-boosted regression model (XGBoost)** to forecast demand and evaluate performance across distinct product demand regimes.

A key focus of this project is understanding *where and why* forecasting errors occur by analyzing model performance across product clusters with different demand stability, price sensitivity, and promotions.

---

## Problem Statement
Accurate demand forecasting is important for inventory planning, pricing strategies, and promotions in retail. However, product demand often varies significantly across items due to differences in price level, discounting behavior, and baseline demand stability.

This project aims to:
- Forecast weekly product demand
- Segment products into interpretable behavioral clusters
- Evaluate forecast performance by cluster
- Translate modeling results into operational insights

---

## Data & Features
The data used in this project was a part of the University of Nicosia - Featured Prediction Competition, which can be found here on Kaggle.com: https://www.kaggle.com/competitions/m5-forecasting-accuracy/overview. 

The dataset consists of weekly product-level sales and pricing information.

Key engineered features include:
- Lagged demand features (previous weeks)
- Rolling statistics (moving averages and variability)
- Price levels and discount depth
- Historical demand trends

---

## Product Segmentation
Products are clustered based on demand behavior, pricing stability, and discount sensitivity. The resulting clusters capture distinct demand regimes, including:
- High-volume stable staples
- Promotion-driven low-volume products
- Niche but highly predictable items
- Premium, low-volume products
- High-volume, highly promotion-sensitive items

---

## Modeling Approach
A **XGBoost regression model** is trained to predict weekly demand using engineered time series and pricing features, and product-based clusters.

Model evaluation includes:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² score
- Cluster-level error analysis

---

## Results
The model achieves solid overall forecasting performance, explaining over 60% of demand variance. Performance varies meaningfully across clusters:
- Stable products exhibit low and tightly distributed errors
- Promotion-driven products show higher variance and occasional large errors
- Absolute error scales logically with demand volume

Cluster-level analysis confirms that forecasting difficulty aligns with demand volatility rather than random model failure.

---

## Limitations & Future Work
- The model does not incorporate explicit future promotion calendars, limiting accuracy during promotional demand spikes.
- Factors such as holidays, seasonality indicators, and macroeconomic signals are not included.
- A single model may underperform for highly specialized product segments.

Future improvements could include cluster-specific models, explicit promotion features, seasonality indicators, and probabilistic forecasting to better quantify uncertainty.

---

## Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- K-Means Clustering
- Matplotlib

---

## Key Takeaway
This project demonstrates how combining **time series modeling with product segmentation** provides deeper insight into forecast performance, highlights operational risk, and supports more informed inventory and pricing decisions.


