# 📘 Student Performance Prediction Using Machine Learning
This project analyzes a synthetic student performance dataset to understand which factors most strongly influence final grades and to build predictive machine learning models. The goal is to compare linear, regularized, nonlinear, and pipeline-based models to determine which approach generalizes best.

## 🚀 Project Overview

This study predicts Final Grade using five predictors:
- Hours Studied
- Previous Scores
- Extracurricular Activities
- Sleep Hours
- Sample Question Papers Practiced

To evaluate model performance, I implemented:
- Multiple Linear Regression (baseline)
- Polynomial Ridge, Lasso, ElasticNet Regression
- Random Forest Regression
- Pipelines with StandardScaler + PolynomialFeatures + Ridge/Lasso
- Cross-Validation analysis (100-fold)
- Overfitting analysis (Train/Test R² gap)
- Final model ranking and comparison

## 📊 Key Findings 
**1. Best Model**
The top-performing model was:
- Polynomial Ridge Regression (degree=2, alpha=10)

It achieved the best balance of:
- Low Test MSE (~4.24)
- High Test R² (~0.9885)
- Low cross-validation variance
- Minimal overfitting gap
- Stable coefficients, unlike Lasso/ElasticNet

**2. Random Forest Underperformed**
Even though the Random Forest had an extremely high training R² (~0.997), it showed:
- Higher Test MSE (~5.60)
- Very high overfitting gap indicating nonlinear models were unnecessary and trees overfit the dataset.

**3. Pipelines Improved Consistency**
The use of Pipeline():
- Standardized preprocessing
- Prevented train/test leakage
- Improved reproducibility
- Produced results nearly identical to manual regularized models

## 🔍 Feature Insights

Across models, the strongest predictors of final grade were:

**1. Previous Scores**
Most powerful linear predictor; strong correlation with Final Grade.
**2. Hours Studied**
Second most important; consistent upward grade trend.
**3. Sample Papers Practiced**
Smaller but meaningful contribution.
**4. Sleep Hours & Extracurriculars**
Small, sometimes slightly negative coefficients — meaning:
- Too many activities can slightly reduce study time.
- Sleep has a mild optimal range effect.

## 📈 Visualizations Included
✔ Correlation matrix
✔ Heatmaps
✔ Model comparison bar charts
✔ R² and MSE comparisons
✔ Overfitting gap comparison
✔ Feature importance from Random Forest
✔ Polynomial vs linear model effects

## 🧾 Conclusion
Machine learning can reliably predict student final grades using simple academic and behavioral variables.
This project shows that:
- Regularized polynomial models outperform basic linear regression.
- Tree models may overfit when the underlying relationship is smooth and nearly linear.
- A student’s past performance and study time are the strongest drivers of final grade.
- Pipelines ensure reliable, production-quality ML workflows.
