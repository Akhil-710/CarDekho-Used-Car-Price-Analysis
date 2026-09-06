# CarDekho-Used-Car-Price-Analysis

## Project Overview

This project analyzes used-car pricing data to understand the factors influencing resale prices and to build a machine learning model for used-car price prediction.

The project covers the complete data analytics workflow:

**Data Cleaning → Exploratory Data Analysis → Feature Engineering → Machine Learning → Model Evaluation → Power BI Dashboard → Business Insights**

---

## Objectives

- Analyze used-car pricing patterns
- Identify important factors affecting selling price
- Understand depreciation across different vehicle categories
- Study the impact of fuel type, seller type and transmission
- Build a machine learning model to predict selling price
- Create an interactive Power BI dashboard for business insights

---

## Dataset

The dataset contains information about used cars including:

- Car Name
- Manufacturing Year
- Selling Price
- Present Price
- Kilometers Driven
- Fuel Type
- Seller Type
- Transmission
- Previous Owners

After cleaning and feature engineering, the dataset contains:

- **299 observations**
- **13 features**

### Engineered Features

The following features were created:

- `Car_Age`
- `Depreciation`
- `Depreciation_Percent`
- `Mileage_Per_Year`

---

## Data Cleaning

The following preprocessing steps were performed:

- Checked for missing values
- Checked for duplicate records
- Verified data types
- Checked for invalid values
- Investigated statistical outliers
- Retained legitimate high-value vehicles instead of removing them automatically

The final dataset contained:

- **0 missing values**
- **0 duplicate rows**

---

## Exploratory Data Analysis

EDA was performed to understand:

### Univariate Analysis
- Selling price distribution
- Numerical feature distributions
- Categorical feature distributions

### Bivariate Analysis
- Selling Price vs Present Price
- Selling Price vs Year
- Selling Price vs Fuel Type
- Selling Price vs Seller Type
- Selling Price vs Transmission

### Multivariate Analysis
- Correlation analysis
- Correlation heatmap
- Relationship between vehicle characteristics and selling price

### Key Findings

- Present Price has a strong positive relationship with Selling Price.
- Selling Price is strongly right-skewed.
- Diesel vehicles have a higher average selling price than petrol vehicles in this dataset.
- Dealer-sold vehicles have a substantially higher average selling price than individually sold vehicles.
- Automatic vehicles generally show higher selling prices than manual vehicles.
- Vehicle age has a negative relationship with selling price.

---

## Machine Learning

### Target Variable

`Selling_Price`

### Features Used

- Present Price
- Car Age
- Mileage Per Year
- Fuel Type
- Transmission
- Seller Type
- Owner

`Car_Name` was not directly encoded because it contains many unique values relative to the dataset size.

---

## Models Evaluated

The following models were evaluated:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Log-Transformed Linear Regression

The target variable was log-transformed because the selling-price distribution was strongly right-skewed.

---

## Final Model

The final selected model was:

**Linear Regression with Log-Transformed Target**

### Test Set Performance

| Metric | Result |
|---|---:|
| R² Score | **0.897** |
| MAE | **0.94 lakh** |
| RMSE | **1.63 lakh** |

The log-transformed model performed better than the raw Linear Regression model on the held-out test set.

---

## Model Interpretation

Important model coefficients included:

- `Seller_Type_Individual`: negative relationship
- `Car_Age`: negative relationship
- `Owner`: negative relationship
- `Transmission_Manual`: negative relationship
- `Fuel_Type_Diesel`: positive relationship
- `Present_Price`: positive relationship

Because the model uses a log-transformed target, coefficients should be interpreted on the log scale rather than as direct changes in selling price.

---

## Power BI Dashboard

The Power BI dashboard provides an interactive overview of the used-car market.

### Dashboard Includes

- Average Selling Price
- Average Present Price
- Total Cars
- Average Car Age
- Average Selling Price by Fuel Type
- Average Selling Price by Seller Type
- Average Selling Price by Transmission
- Average Selling Price by Year
- Present Price vs Selling Price scatter plot
- Interactive filters for:
  - Fuel Type
  - Seller Type
  - Transmission
  - Year

### Dashboard Preview

![CarDekho Dashboard](dashboard/dashboard_preview.png)

---

## Business Insights

### 1. Present Price is a major predictor

Present Price has a strong positive relationship with Selling Price, making it one of the most important variables for price prediction.

### 2. Seller type matters

Dealer-sold cars have a considerably higher average selling price than individually sold cars in this dataset.

### 3. Vehicle age affects resale value

Older vehicles generally have lower selling prices, indicating depreciation over time.

### 4. Transmission influences pricing

Automatic vehicles tend to have higher selling prices than manual vehicles in the analyzed dataset.

### 5. Used-car prices are highly skewed

A small number of expensive vehicles significantly increase the average selling price. Therefore, median and distribution-based analysis are also important.

---

## Limitations

- The dataset contains only 299 observations.
- The number of high-value vehicles is relatively small.
- Model performance can vary significantly depending on the train-test split.
- The reported test-set performance should not be treated as a guarantee of real-world prediction accuracy.
- `Car_Name` was excluded from the ML model because of its high cardinality relative to the dataset size.

---

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
- Power BI
- Git & GitHub

---

## Project Workflow

Dataset
   ↓
Data Understanding
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Feature Engineering
   ↓
Feature Selection
   ↓
Encoding
   ↓
Train-Test Split
   ↓
Machine Learning
   ↓
Model Evaluation
   ↓
Final Model
   ↓
Power BI Dashboard
   ↓
Business Insights
