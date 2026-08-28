# 🌧️ Bangladesh Temperature & Rainfall — Linear Regression

A linear regression project predicting monthly rainfall in Bangladesh using historical temperature, month, and year data (1901–2015).

## 📊 Dataset

- **Source:** [Temp and Rain — Bangladesh](https://www.kaggle.com/datasets/mahmudulsakib2019/temp-and-rain) (Kaggle)
- **File:** `Temp_and_rain.csv`
- **Rows:** 1,380 monthly records
- **Columns:**
  | Column | Description |
  |--------|-------------|
  | `tem`  | Average monthly temperature (°C) |
  | `Month`| Month of the year (1–12) |
  | `Year` | Year (1901–2015) |
  | `rain` | Monthly rainfall (mm) |

No missing values in the dataset.

## 🎯 Objective

Predict monthly **rainfall (`rain`)** using **temperature (`tem`)**, **Month**, and **Year** as features, via multiple linear regression.

## 🛠️ Workflow

1. **Data loading & inspection** — `pandas` (`.head()`, `.info()`, `.describe()`)
2. **Exploratory Data Analysis (EDA)**
   - Jointplots: temperature vs. rainfall, month vs. rainfall
   - Pairplot across all features
   - Correlation heatmap
   - Regression plot (`lmplot`)
3. **Train/test split** — 70/30 split via `scikit-learn`
4. **Model training** — `LinearRegression` from `scikit-learn`
5. **Statistical summary** — `statsmodels` OLS regression (coefficients, p-values, R²)
6. **Predictions & evaluation**
   - Actual vs. predicted scatter plot
   - Mean Absolute Error (MAE)
   - Mean Squared Error (MSE)
   - Root Mean Squared Error (RMSE)
7. **Residual analysis** — residual distribution plot + Q-Q plot to check normality assumption

## 📈 Results

| Metric | Value |
|--------|-------|
| R² (test) | ~0.50 |
| MAE | ~113.7 mm |
| MSE | ~22,089.6 |
| RMSE | ~148.6 mm |

Rainfall in Bangladesh is strongly seasonal (monsoon-driven), so a plain linear model using `Month` as a raw numeric feature only partially captures the pattern — December and January are numerically far apart but climatically similar. This limits model performance.

## 🚀 Possible Improvements

- Encode `Month` cyclically using sine/cosine transforms to capture seasonality
- Add interaction terms (e.g. `tem × Month`)
- Try non-linear models (polynomial regression, random forest, gradient boosting)
- Incorporate additional climate features (humidity, pressure, wind speed) if available

## 📦 Requirements

```
pandas
matplotlib
seaborn
scikit-learn
statsmodels
scipy
```

Install with:
```bash
pip install pandas matplotlib seaborn scikit-learn statsmodels scipy
```

## ▶️ Usage

1. Clone the repository
   ```bash
   git clone <your-repo-url>
   cd <your-repo-name>
   ```
2. Place `Temp_and_rain.csv` in the project directory (or update the file path in the notebook)
3. Open and run the notebook
   ```bash
   jupyter notebook Bangladesh_Regression_Task.ipynb
   ```

## 📁 Project Structure

```
.
├── Temp_and_rain.csv               # Dataset
├── Bangladesh_Regression_Task.ipynb  # Main analysis notebook
└── README.md                       # Project documentation
```

## 📝 License

This project is for educational purposes as part of an AI/ML lab task.
