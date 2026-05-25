# 🏠 House Price Prediction
### Kaggle Competition — Advanced Regression Techniques

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python) ![Kaggle](https://img.shields.io/badge/Kaggle-Competition-20BEFF?logo=kaggle) ![Status](https://img.shields.io/badge/Status-Submitted-success)

---

## 📌 Overview

Predicted final sale prices of residential homes in Ames, Iowa using 79 explanatory variables describing almost every aspect of the property. This was my first regression project as part of a structured Data Science portfolio roadmap.

**Competition:** [House Prices — Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)

| Metric | Value |
|---|---|
| Evaluation Metric | RMSLE (Root Mean Squared Log Error) |
| My Score | **0.12686** |
| Leaderboard Rank | **~1387** |
| Baseline (predicting mean) | ~0.40+ |

---

## 📁 Project Structure

```
house-price-prediction/
│
├── data/
│   ├── train.csv
│   ├── test.csv
│   └── sample_submission.csv
│
├── notebooks/
│   └── house_price_prediction.ipynb
│
├── submission/
│   └── submission.csv
│
└── README.md
```

---

## 🔍 Approach

### 1. Exploratory Data Analysis (EDA)
- Analyzed distribution of `SalePrice` — found right-skew, applied log transformation
- Identified missing values across 79 features
- Explored correlations between numerical features and target
- Visualized categorical features vs. sale price using box plots

### 2. Data Preprocessing
- Handled missing values (median for numerical, mode for categorical)
- Encoded categorical variables
- Removed outliers in `GrLivArea` vs `SalePrice`
- Applied `np.log1p` transformation to the target variable

### 3. Feature Engineering
- Created interaction features from existing columns
- Dropped low-variance and high-null columns

### 4. Modelling
- Trained and evaluated multiple regression models
- Used cross-validation (5-fold) to avoid overfitting
- Final predictions inverse-transformed using `np.expm1`

### 5. Submission
- Generated `submission.csv` and submitted to Kaggle
- Achieved RMSLE of **0.12686**

---

## 📊 Results

| Model | CV RMSLE |
|---|---|
| Linear Regression (baseline) | ~0.18 |
| Random Forest | ~0.14 |
| Final Model | **~0.12686** |

---

## 🚀 What I'd Improve Next

- [ ] More aggressive feature engineering (e.g. `TotalSF = TotalBsmtSF + 1stFlrSF + 2ndFlrSF`)
- [ ] Model-based imputation for missing values instead of median/mode
- [ ] Log-transform other skewed numerical features beyond `SalePrice`
- [ ] Try stacking / blending (Random Forest + XGBoost + Ridge) for sub-0.115
- [ ] Hyperparameter tuning with `GridSearchCV` or `Optuna`

---

## 🛠️ Tech Stack

- **Language:** Python 3.x
- **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
- **Environment:** Jupyter Notebook
- **Platform:** Kaggle Notebooks

---

## 📚 Learnings

This project was my first end-to-end regression pipeline. Key takeaways:

- Log-transforming a skewed target variable significantly improves model performance
- Missing value strategy matters more than I initially expected
- Cross-validation score is a much more reliable indicator than training accuracy
- Feature engineering has more impact than model choice at this level

---

## 🔗 Links

- [Kaggle Competition Page](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)
- [My Kaggle Profile](https://www.kaggle.com/nothingspecial0123) *(update with your profile link)*

---

