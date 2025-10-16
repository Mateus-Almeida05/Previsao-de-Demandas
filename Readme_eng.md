<img width="343" height="240" alt="image" src="https://github.com/user-attachments/assets/43f94828-b572-40e4-972e-0476bee8e333" />

# **Demand Forecasting**

**1\. Introduction**

This project aims to develop, test, and compare demand forecasting models for a retail store network, evaluating not only the statistical accuracy of the forecasts but also the financial impact of each approach. The work covers all stages of the data science lifecycle — from data understanding to cost analysis resulting from forecast errors — with a focus on supporting strategic supply decisions and reducing operational costs.

**2\. Problem Solved**

The main challenge is to predict future product demand as accurately as possible to minimize two types of financial losses:

* Inventory cost – when the forecast is higher than the actual demand, resulting in excess stock.

* Opportunity cost – when the forecast is lower than the actual demand, resulting in stockouts and lost.

The goal is to identify the model that best balances predictive accuracy and financial impact across different stores and product families.

**3\. Problem-Solving Approach**

The project was divided into four stages:

3.1. Data Understanding and Preparation

* Exploratory analysis to identify sales patterns, seasonality, and outliers.

* Enrichment of the dataset with external variables (e.g., oil price, holidays, promotions).

* Creation of temporal features and sales lags to capture historical trends.

3.2. Modeling and Training

* Evaluation of the current model (baseline).

* Training and comparison of several algorithms: Linear Regression, LightGBM, CatBoost, Gradient Boosting, XGBoost, and LSTM.

* Hyperparameter optimization with Optuna.

* Development of single (global) and segmented models by store.

3.3. Model Segmentation

* Creation of independent pipelines for stores with distinct behavior.

* Comparison between the global and segmented models in terms of error and stability.

3.4. Financial Evaluation

* Calculation of inventory and opportunity costs based on forecasts.

* Comparison of models considering total cost and error metrics (MAE and RMSE).

**4.Project Structure**

Projeto\_Previsao\_Demandas  
├── 01\_entendimento\_dados.py         \# Exploratory analysis and data preparation  
├── 02\_modelagem.py                  \# Model training and comparison  
├── segmentacao\_de\_modelos.py        \# Store-level model segmentation  
├── avaliacao\_financeira.py          \# Cost calculation and financial comparison  
├── dados/                           \# Training, validation, and cost datasets  
└── modelos/                         \# Saved pipelines (.pkl)

**5\. Technologies Used**

* Language: Python

* Main Libraries:

  * Data manipulation: pandas, numpy

  * Visualization: matplotlib, seaborn

  * Modeling: scikit-learn, lightgbm, catboost, xgboost, tensorflow

  * Hyperparameter optimization: optuna

  * Model serialization: joblib

**6\. Results** 

The developed model achieved the best balance between accuracy and financial cost, reducing the total cost by more than 90% compared to the existing model. The segmented models showed similar accuracy but with a slightly higher total cost.

| Model | MAE | RMSE | Total Cost (R$) |
| :---: | :---: | :---: | :---: |
| Current | 3.287 | 10.898 | 626.804.845,55 |
| Single (CatBoost) | 471 | 1.278 | 36.259.814,83 |
| Segmented | 517 | 1.237 | 43.274.465,63 |

**7\. Conclusion**

The project demonstrated that the application of advanced data analysis and machine learning techniques, combined with a structured financial approach, can significantly optimize the demand forecasting process. The integration of statistical analysis, feature engineering, and cost measurement not only improved prediction accuracy but also helped to understand the economic impact of each modeling decision. As a result, predictive analytics was transformed into a strategic tool, guiding inventory planning and store replenishment more efficiently and in alignment with business realities. In addition to reducing operational costs and losses caused by excess or insufficient stock, the project provides a solid foundation for future decision-making, showing how data intelligence can directly contribute to profitability and operational sustainability.

