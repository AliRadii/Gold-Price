# 🟡 GLD Price Prediction (Gold ETF) — Linear Regression, SVR & KNN

Predicting **GLD (SPDR Gold Shares ETF)** price using market and macroeconomic indicators with multiple regression models.  
This project includes full **EDA**, **preprocessing**, and a **model comparison** between classic ML regressors.

---

## ✨ Highlights
✅ Clean EDA with visual insights  
✅ Outlier detection & removal (IQR method)  
✅ Feature scaling using **MinMaxScaler**  
✅ Trains and compares **3 regression models**:
- Linear Regression (Baseline)
- Support Vector Regression (SVR)
- K-Nearest Neighbors Regression (KNN)

✅ Evaluation using:
- **R² Score**
- **MAE**
- **MSE**

---

## 📌 Dataset
File: `gld_price_data.csv`

**Target**
- `GLD` → Gold ETF price

**Features**
- `SPX` → S&P 500 Index
- `USO` → Oil ETF proxy
- `SLV` → Silver ETF proxy
- `EUR/USD` → Euro to USD exchange rate

**Other**
- `Date` → removed before modeling

---

## 🔎 Exploratory Data Analysis (EDA)
The notebook explores the dataset using:
- **Pairplot** (feature relationships)
- **Scatterplots** (e.g., `SLV` vs `GLD`)
- **Histograms** (distribution of features)
- **Boxplots** (outlier visualization)
- **Correlation heatmap** (feature importance/relationships)

---

## 🧹 Preprocessing
Steps applied before training:

### ✅ 1) Drop non-numeric column
- `Date` removed

### ✅ 2) Outlier Removal (IQR Method)
Outliers are removed from numeric columns using:

- Q1 (25th percentile)
- Q3 (75th percentile)
- IQR = Q3 − Q1  
- Keep values inside `[Q1 − 1.5*IQR, Q3 + 1.5*IQR]`

### ✅ 3) Feature Scaling
- `MinMaxScaler` is applied to scale features into `[0, 1]`

### ✅ 4) Train/Test Split
- `test_size = 0.2`
- `random_state = 42`

---

## 🤖 Models Used

### 1) Linear Regression (Baseline)
A simple baseline regression model used for comparison.

### 2) SVR (Support Vector Regression)
Effective for non-linear patterns (depending on kernel choice).

### 3) KNN Regressor
Predicts target value based on the nearest neighbors in feature space.

---

## 📊 Evaluation Metrics
Each model is evaluated using:

- **R² Score** (higher is better)
- **MAE** (lower is better)
- **MSE** (lower is better)


