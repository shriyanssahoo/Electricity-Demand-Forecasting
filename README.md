\# ⚡ Electricity Demand Forecasting



This project focuses on forecasting electricity demand using both \*\*daily data\*\* and \*\*high-frequency (15-minute interval) time series data\*\*. Multiple modeling approaches were explored, including baseline methods, statistical models, and machine learning techniques.



\---



\## 📊 Project Overview



The objective of this project is to:

\- Understand electricity demand patterns

\- Build forecasting models at different granularities

\- Compare traditional statistical approaches with modern ML models

\- Identify the best-performing model for each dataset



\---



\## 📁 Datasets Used



\### 1. Daily Dataset

\- Duration: \~3 years

\- Target: `max\_demand\_met\_mw`

\- Used for long-term forecasting



\### 2. Time Series Dataset (15-min)

\- Duration: \~1 year

\- Frequency: 15-minute intervals

\- Target: `demand\_met\_mw`

\- Used for short-term forecasting



\---



\## ⚙️ Feature Engineering



The following features were created:



\- \*\*Time-based:\*\*

&#x20; - Day of week, month, hour

&#x20; - Weekend indicator



\- \*\*Cyclical encoding:\*\*

&#x20; - `sin` / `cos` transformations



\- \*\*Lag features:\*\*

&#x20; - Daily: lag\_1, lag\_7, lag\_30

&#x20; - 15-min: lag\_1, lag\_96



\- \*\*Rolling statistics:\*\*

&#x20; - Mean and standard deviation



\- \*\*Event-based:\*\*

&#x20; - Festival indicators (`is\_festival`, `is\_pre`, `is\_post`)



\---



\## 🔀 Data Splitting Strategy



Time-based split to avoid leakage:

\- Train (\~70%)

\- Validation (\~15%)

\- Test (\~15%)



\---



\## 📉 Models Implemented



\### 1. Baseline Models

\- Mean Model

\- Naive Model

\- Seasonal Naive

\- Drift Model

\- Exponential Smoothing (SES, Holt, Holt-Winters)



\---



\### 2. Statistical Models

\- Autoregressive (AR)

\- ARIMA

\- SARIMA

\- SARIMAX



\---



\### 3. Machine Learning Models

\- Random Forest

\- XGBoost

\- Linear Regression (tested, later excluded)



\---



\## 📊 Results Summary



\### 🔹 Daily Forecasting

\- Best Models:

&#x20; - Random Forest

&#x20; - XGBoost

\- Performance:

&#x20; - \*\*MAPE ≈ 1.8%\*\*



\---



\### 🔹 15-min Forecasting

\- Best Model:

&#x20; - \*\*XGBoost (Final Winner)\*\*

\- Performance:

&#x20; - \*\*MAPE ≈ 0.56%\*\*



\---



\## 🔍 Key Insights



\- Baseline models perform surprisingly well for short-term forecasting

\- Statistical models struggle with complex and non-linear patterns

\- Machine learning models significantly outperform traditional approaches

\- High-frequency data benefits more from ML due to:

&#x20; - Non-linear dependencies

&#x20; - Strong short-term patterns



\---



\## 🧠 Final Conclusion



Machine learning models, especially \*\*XGBoost\*\*, are highly effective for electricity demand forecasting, particularly for high-frequency (15-minute interval) data. These models capture both temporal patterns and non-linear relationships, leading to superior predictive performance.



\---



\## 🚧 Limitations



\- No weather or external data used

\- Limited hyperparameter tuning

\- Models rely only on historical patterns

\- Sudden anomalies or external shocks not captured



\---



\## 🚀 Future Work



\- Incorporate weather data (temperature, humidity)

\- Try deep learning models (LSTM, Transformers)

\- Perform hyperparameter optimization

\- Build real-time forecasting pipeline



\---



\## 🛠️ Tech Stack



\- Python

\- Pandas, NumPy

\- Scikit-learn

\- XGBoost

\- Statsmodels

\- Matplotlib / Seaborn



\---



\## 📌 How to Run



```bash

\# Clone the repository

git clone <your-repo-link>



\# Install dependencies

pip install -r requirements.txt



\# Run notebooks

jupyter notebook

