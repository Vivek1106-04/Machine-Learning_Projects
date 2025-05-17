# 🏠 House Price Prediction - Custom ML Regression Model

This project is based on the Kaggle competition: **[House Prices - Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)**.

## 📌 Project Objective

To predict the final sale price of homes using various features like location, square footage, number of rooms, year built, etc., by building a **custom regression model from scratch with Lasso regularization** (no scikit-learn models used for training).

---

## 📁 Dataset Source

We used the official Kaggle dataset.  
To use the dataset:
1. Visit the competition page [here](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data).
2. Download `train.csv` and `test.csv`.
3. Place both files in your project folder.

---

## 🛠️ Steps Implemented

### 1. Data Preprocessing
- Handled missing values using domain logic.
- Converted categorical variables using one-hot encoding.

### 2. Data Visualization
- Used `seaborn` and `matplotlib` for:
  - Missing value heatmaps
  - Distribution plots
  - Correlation heatmaps
  - Pairplots and t-SNE

### 3. Feature Engineering
- Created meaningful features (like total area, age of house).
- Removed highly collinear or redundant features.

### 4. Model Building
- Implemented **Lasso regression with gradient descent** manually.
- Compared with Ridge regression.
- Evaluated using RMSE.

---

