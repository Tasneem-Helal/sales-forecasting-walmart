# Sales Forecasting Using Walmart Dataset

This project builds predictive models to forecast **weekly sales** across Walmart stores and departments based on historical data. The workflow includes data cleaning, feature engineering, regression modeling, time-aware validation, and performance evaluation.

---

## Objective

- Forecast future weekly sales from historical data.
- Generate meaningful time-based features (lag values, rolling averages).
- Apply regression models and compare performance.
- Analyze trends, seasonality, and feature importance.

---

## Project Structure

```
|- results/
   |- model_performance_summary.csv   
|- src/
   |- Sales_Forecasting.ipynb         
|- .gitignore
|- README.md
|- requirements.txt
```

---

## Tools & Libraries

- Python  
- pandas, numPy  
- matplotlib
- scikit-learn, statsmodels  
- xgboost, lightgbm
- kagglehub  

---

## Methodology

1. **Data Loading & Cleaning**  
   - Download Walmart Sales Forecast dataset from Kaggle.  
   - Merge `train`, `test`, `features`, and `stores`.  
   - Handle missing values and remove outliers.

2. **Feature Engineering**  
   - Extract time-based features: `Year`, `Month`, `Week_of_Year`, and `Day`.  
   - Generate lag features and rolling averages (4-week & 12-week).

3. **Model Development**  
   - Baseline (lag-based), Linear Regression, Random Forest, XGBoost, and LightGBM.  
   - Time-aware validation using **TimeSeriesSplit**.  
   - ⚠️ Random Forest training may take ~10 minutes. Reduce `n_estimators` for faster testing if needed.

4. **Model Evaluation**  
   - Metrics: MAE, RMSE  
   - Results saved to `/results/model_performance_summary.csv`.

5. **Visualization & Insights**  
   - Actual vs. predicted sales trends  
   - Seasonal decomposition and rolling averages  
   - Feature importance for XGBoost & LightGBM

---

## Results

⚠️ XGBoost achieved the best performance (lowest RMSE). Detailed results will be generated in `/results/model_performance_summary.csv` when running the notebook.

---

## How to Run

1. Clone the repository:
```bash
git clone https://github.com/Tasneem-Helal/sales-forecasting-walmart.git
cd sales-forecasting-walmart/src
```

2. Install dependencies:
```bash
pip install -r ../requirements.txt
```

3. Run the notebook:
```bash
jupyter notebook src/Sales_Forecasting.ipynb
```

---

## Dataset

- **Source:** [Walmart Sales Forecast – Kaggle](https://www.kaggle.com/datasets/aslanahmedov/walmart-sales-forecast/data?select=features.csv)  
- **License:** Data files © Original Authors

---

## Future Improvements

- Hyperparameter tuning (Optuna/GridSearchCV) to further optimize model performance
- Incorporate external factors (e.g., weather, promotions) to improve accuracy
- Extend forecasting horizon to multiple weeks using recursive or direct multi-step predictions

---

## Author

**Tasneem Helal**  
Mechatronics Engineer | Machine Learning Enthusiast  
[LinkedIn](https://linkedin.com/in/tasneemhelal) | [GitHub](https://github.com/Tasneem-Helal)

