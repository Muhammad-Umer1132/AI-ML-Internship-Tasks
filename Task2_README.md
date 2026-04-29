#  Task 2: Predict Future Stock Prices (Short-Term)
---
## Objective
Use historical stock market data fetched via the `yfinance` Python library to predict the **next day's closing price** of Apple Inc. (`AAPL`) using regression models.
---
##  Dataset
- **Source:** Yahoo Finance via `yfinance` Python library (real live data — no manual download needed)
- **Stock Selected:** Apple Inc. (`AAPL`)
- **Time Range:** 2022-01-01 → 2024-12-31
- **Raw Features:** Open, High, Low, Close, Volume
---
##  Feature Engineering
Beyond the raw OHLCV features, the following were engineered to improve model performance:

| Feature | Description |
|---|---|
| `Price_Range` | Daily High minus Low |
| `Price_Change` | Close minus Open (intraday movement) |
| `MA_5` | 5-day moving average of Close |
| `MA_10` | 10-day moving average of Close |
| `Volatility` | 5-day rolling standard deviation of Close |

---
##  Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical operations |
| `yfinance` | Fetching real stock data from Yahoo Finance |
| `scikit-learn` | Model training, scaling, and evaluation |
| `matplotlib` | Plotting charts |
| `seaborn` | Statistical visualizations |

---
##  Models Applied

### 1. Linear Regression
A simple, interpretable baseline model that finds the best linear relationship between input features and the next day's closing price.

### 2. Random Forest Regressor
An ensemble of 200 decision trees that captures non-linear relationships in financial data. Generally outperforms linear models on real-world stock data.

---
##  Visualizations Produced
1. **Historical Price & Volume Chart** — Overview of AAPL stock over 2 years
2. **Actual vs Predicted Closing Prices** — Line chart for both models on the test set
3. **Scatter Plot** — Predicted vs Actual (closer to diagonal = better)
4. **Feature Importance Chart** — Which features the Random Forest relied on most

---
##  Key Results & Findings

| Metric | Linear Regression | Random Forest |
|---|---|---|
| MAE ($) | higher | **lower ** |
| RMSE ($) | higher | **lower ** |
| R² Score | lower | **higher ** |

- **Random Forest outperforms Linear Regression** — stock prices follow non-linear dynamics that linear models cannot fully capture
- **Moving averages (MA_5, MA_10)** ranked as the most important features in the Random Forest
- **Chronological train/test split (80/20)** was used — data was never shuffled to prevent leakage of future information into training

---
##  Key Takeaways
1. Moving averages smooth out short-term noise and are highly predictive of next-day prices
2. Random Forest captures complex, non-linear market patterns that Linear Regression misses
3. Time-series data must always be split **chronologically** — random shuffling causes data leakage and inflated scores
4. A high R² score does not guarantee profitable trading — real trading requires additional risk management strategies

---
##  File Structure
```
Task2_Stock_Price_Prediction.ipynb   ← Main Jupyter Notebook (all code + visualizations)
README.md                            ← This file
```
---
##  How to Run

```bash
# Install required libraries
pip install pandas numpy matplotlib seaborn scikit-learn yfinance
# Launch the notebook
jupyter notebook Task2_Stock_Price_Prediction.ipynb
```
> **Note:** The dataset is fetched **automatically** from Yahoo Finance when you run the notebook. No manual CSV download is required.
---

