# Housing Price Regression Analysis using Linear and Ridge Regression

![Python](https://img.shields.io/badge/Python-3.10-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![status](https://img.shields.io/badge/status-completed-green)
![project](https://img.shields.io/badge/project-regression-blue)
![model](https://img.shields.io/badge/model-Linear--Regression-red)
![model](https://img.shields.io/badge/model-Ridge--Regression-purple)

## Overview
This project implements a complete regression analysis pipeline to predict housing prices using structured housing data.

The workflow includes:
- Data exploration and inspection
- Data cleaning and missing value handling
- Skewness detection and transformation
- Feature scaling and preprocessing
- Linear Regression modeling
- Ridge Regression modeling
- Model evaluation and comparison
- Regression assumption checking
- Residual analysis and interpretation

This project demonstrates fundamental and advanced regression modeling techniques using scikit-learn.

## Objective
The goal of this project is to build regression models that predict median housing value (MEDV) based on housing and socioeconomic features.

## Dataset Description
Dataset file: HousingData.csv
Each row represents one housing district.

### Key Features
| Feature | Description |
|--------|-------------|
| CRIM | Crime rate |
| ZN | Residential land zoning |
| INDUS | Industrial proportion |
| CHAS | Charles River dummy variable |
| NOX | Nitric oxide concentration |
| RM | Average number of rooms |
| AGE | Age of houses |
| DIS | Distance to employment centers |
| RAD | Accessibility to highways |
| TAX | Property tax rate |
| PTRATIO | Student-teacher ratio |
| B | Demographic variable |
| LSTAT | Lower status population percentage |
| MEDV | Median house value (Target) |

## Data Preprocessing
Several preprocessing steps were applied to improve model performance and reliability.

### Missing Value Handling
Missing values were filled using median imputation:
```
df_filled = df.fillna(df.median())
```
Median is more robust to outliers compared to mean.

### Skewness Detection and Transformation
MEDV was highly right-skewed.
Log transformation was applied:
```
df['MEDV'] = log(MEDV)
```
Result:
Skewness improved from:
```
1.108 → 0.121
```
This improved normality and stabilized variance.

### Feature Scaling
StandardScaler was applied to normalize features:
```
StandardScaler()
```
This ensures fair coefficient estimation and stable training.

### Train-Test Split
Dataset was split into:
```
80% Training
20% Testing
```

## Exploratory Analysis
The following visualizations were generated:
medv_boxplot.png  
Distribution and outlier visualization of MEDV
lstat_vs_medv.png  
Relationship between socioeconomic status and housing price
correlation_heatmap.png  
Feature correlation analysis

Key findings:
- RM has strong positive correlation with MEDV
- LSTAT has strong negative correlation with MEDV
- Several features show meaningful predictive relationships

## Models Implemented
Two regression models were implemented and compared.

### 1. Linear Regression (Baseline)
A standard linear regression model without regularization.
Advantages:
- Simple
- Interpretable
- Strong baseline performance
Performance:
```
R²   = 0.7420
RMSE = 0.1892
```
---

### 2. Ridge Regression (Regularized)
Ridge regression adds L2 regularization to prevent overfitting.
Performance:
```
R²   = 0.7413
RMSE = 0.1894
```
Result:
Ridge did not significantly improve performance.

## Model Evaluation Metrics
The following metrics were used:
- R² Score
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)
- Residual Analysis

## Residual Analysis
Residual plots were generated:
```
residual_plot.png
```
Findings:
- Residuals are randomly scattered around zero
- No strong systematic pattern
- Linear regression assumptions are reasonably satisfied

## Feature Importance (Coefficient Analysis)
Strongest positive predictor:
```
RM (Number of rooms)
```
Strongest negative predictor:
```
LSTAT (% lower socioeconomic population)
```
Interpretation:
- More rooms → higher house price
- Higher LSTAT → lower house price

## Model Comparison
Results saved in:
```
model_performance_comparison.csv
```
Summary:
Linear Regression performed slightly better and was selected as the final model due to simplicity.

## Project Structure
```
project/
│
├── analysis.ipynb
├── HousingData.csv
│
├── medv_boxplot.png
├── lstat_vs_medv.png
├── correlation_heatmap.png
├── residual_plot.png
│
├── model_performance_comparison.csv
├── report.md
└── README.md
```

## Technologies Used
Python
Libraries:
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- scipy

## How to Run
Install dependencies:
```
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```
Run notebook:
```
jupyter notebook
```
Open:
```
analysis.ipynb
```
Run all cells.

## Machine Learning Concepts Demonstrated
- Data cleaning
- Missing value imputation
- Skewness correction
- Feature scaling
- Linear Regression
- Ridge Regression
- Regularization
- Model evaluation
- Residual analysis
- Regression assumptions
- Model comparison

## Author
Nadine Octavia  
Machine Learning Project — Housing Price Regression Analysis