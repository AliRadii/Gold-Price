# GOLD Price Prediction (Gold ETF) — EDA + Linear Regression

This repo predicts **GLD (SPDR Gold Shares ETF)** price using a small macro/market feature set and a simple baseline model.

It includes:
- Quick **EDA** (pairplot, scatterplots, boxplots, histograms)
- **Correlation heatmap**
- **Outlier removal** using the IQR rule
- **Feature scaling** with `MinMaxScaler`
- Baseline **Linear Regression** model + evaluation

---

## Dataset

File: `gld_price_data.csv`

Columns:
- `Date` (dropped for modeling)
- `SPX` — S&P 500 index
- `USO` — Oil ETF proxy
- `SLV` — Silver ETF proxy
- `EUR/USD` — Euro / US Dollar exchange rate
- `GLD` — Target (Gold ETF price)

---

## Project Workflow

1. Load dataset
2. Drop `Date`
3. EDA:
   - Pairplot for relationships
   - `SLV` vs `GLD` scatter plot
   - Boxplots + histograms (per feature)
   - Correlation heatmap
4. Remove outliers (IQR method) on feature columns
5. Scale features using `MinMaxScaler`
6. Train/Test split (`test_size=0.2`, `random_state=42`)
7. Train `LinearRegression`
8. Evaluate with:
   - `R2`
   - `MAE`
   - `MSE`
9. Visualize predictions vs true values (scatter plot)

---

## Results (reproducible)

Using the exact notebook logic on the included CSV:

- Rows before outlier removal: **2290**
- Rows after outlier removal: **2146**
- Train R² (model.score on train): **0.8913**
- Test R²: **0.8660**
- MAE: **5.2418**
- MSE: **56.8644**

> Notes:
> - This is a **baseline** model (Linear Regression). Performance can improve with stronger models (e.g., XGBoost, RandomForest) and time-aware validation.


