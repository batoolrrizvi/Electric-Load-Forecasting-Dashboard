# Electric Load Forecasting Dashboard

## Overview  
An interactive browser dashboard that combines unsupervised clustering and multiple forecasting approaches to explore hourly electricity demand across ten major U.S. cities.

1. Loading and merging all datasets
2. Data Preprocessing
3. Clustering
4. Predictive Modelling

---

## Clustering
Goal: Group hourly observations by weather and demand patterns.

  A. PCA Visualization: Reduce 7 features (temp, humidity, windSpeed, demand, pressure, precipIntensity, precipProbability) to 2D with PCA for a quick look at structure.
  B. Clustering Methods:
    1. K‑Means: Use the elbow plot on inertia (k = 2–10) to pick k, then assign clusters.
    2. DBSCAN: Find dense areas and mark noise without predefining k.
    3. Hierarchical: Build a dendrogram on a sample, then cut at a chosen distance to form clusters.

## Predictive Modelling:
Goal: Our objective is to forecast next-day hourly electricity demand using weather and temporal features.

  A. Problem Formulation: 24-hour ahead forecasting.
  B. Baseline: Naive forecast = today’s demand at the same hour.
  C. Feature Engineering: lag features, temporal dummies, weather inputs.
  D. Models: Random Forest, XGBoost, SARIMA, LSTM
  E. Validation: Time-series split + GridSearchCV.
  F. Metrics: MAE, RMSE, MAPE.
  G. Ensemble: Stacking of top two models.
  H. Comparison: Baseline vs. each model vs. ensemble.

## To run:
Run command on terminal: python -m http.server 8000

Open index.html in browser:
http://localhost:8000
