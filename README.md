# Delivery Delay Risk Prediction

Predicting late-delivery risk at order time to improve customer experience and operational efficiency in e-commerce.

## Overview
This project builds a machine learning pipeline to identify high-risk delivery orders early, enabling proactive logistics intervention and customer communication. Using the Brazilian Olist e-commerce dataset (~100K orders), we model late-delivery risk under a highly imbalanced setting (~8% late).

## Data
- **Source:** Brazilian E-Commerce Public Dataset by Olist (2016–2018)
- **Target:** `late_delivery` (1 = delivered after estimated date)
- **Features:** seller behavior, customer & seller location, product attributes, freight value, timestamps

## Modeling Approach
We compare imbalance-handling strategies across two model families:
- **Random Forest:** baseline, undersampling, oversampling, class weighting
- **XGBoost:** baseline, resampling, class weighting

**Final Model:** Weighted XGBoost with L2 regularization  
- Optimized for high recall  
- Operating threshold: 0.28  
- Captures ~9× more late deliveries than random selection

## Key Results
- Recall improved from ~9% → ~80%
- Best ROI achieved by targeting the top 5–10% highest-risk orders
- Seller-level behavior and city-level factors are the strongest predictors

## Business Impact
- Fewer unexpected late deliveries
- Reduced complaints and refunds
- More efficient allocation of logistics and customer support resources

## Recommendations
- Use the model as a risk-ranking tool, not a binary classifier
- Prioritize intervention on the top ~8% highest-risk orders
- Extend the model with external signals (weather, traffic, carrier SLAs)

## Team
Jiwoo Jeong · Kyeongmo Kang · Zhihuan Hao · Patrick Farrell  
NYU — Data Science & AI for Business
