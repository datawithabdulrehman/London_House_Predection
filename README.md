# London House Price Prediction 🏠📉

This repository contains a complete machine learning workflow for predicting residential property prices in London. Using a dataset of 1,000 houses with various physical and categorical features, the project covers everything from Data Visualization and Exploratory Data Analysis (EDA) to feature encoding, scaling, model training, and performance evaluation.

## 📌 Project Overview
Predicting house prices is a classic regression problem in machine learning. This project demonstrates how data-driven insights and advanced gradient boosting techniques can accurately estimate property valuations based on features like square footage, location, house type, building age, and interior style.

### Key Workflows:
1. **Exploratory Data Analysis (EDA):** Visualizing distributions (price, log-price) and engineering correlation matrices to identify core price drivers.
2. **Data Preprocessing:** Standardizing numerical values and converting categorical fields into machine-readable formats using One-Hot Encoding.
3. **Model Evaluation:** Implementing and benchmarking multiple algorithms:
   * **Linear Regression** (Baseline model)
   * **Random Forest Regressor** (Ensemble baseline)
   * **XGBoost Regressor** (Advanced gradient boosting)

---

## 📊 Dataset Features
The dataset (`london_houses.csv`) consists of 1,000 property records across 17 distinct columns:

* **Categorical Features:** `Neighborhood` (e.g., Notting Hill, Westminster, Soho), `Garden`, `Garage`, `Property Type` (e.g., Semi-Detached, Apartment), `Heating Type`, `Balcony`, `Interior Style` (e.g., Industrial, Classic, Modern), `View`, `Materials`, and `Building Status`.
* **Numerical Features:** `Bedrooms`, `Bathrooms`, `Square Meters`, `Building Age`, and `Floors`.
* **Target Variable:** `Price (£)`

---

## 📈 Key Visualizations & Insights

### 1. Price Distribution
The house prices exhibit a slightly right-skewed distribution, which stabilizes significantly under log transformation, signaling strong underlying consistency for regression algorithms.

![Price Distribution](price_distribution.png) *(Save your price distribution plot as price_distribution.png and place it in the root folder)*

### 2. Price by Neighborhood
Neighborhood location plays a critical role in property valuation. Prime locations like Chelsea and Kensington median prices stand significantly higher compared to other regions.

![Price by Neighborhood](neighborhood_boxplot.png) *(Save your neighborhood boxplot as neighborhood_boxplot.png and place it in the root folder)*

---

## 🚀 Model Performance Summary

To ensure high factual precision, the models were validated on a 30% test split (700 train / 300 test) using Root Mean Squared Error (**RMSE**), Mean Absolute Error (**MAE**), and the R-squared (**R²**) score:

| Model | RMSE | MAE | R² Score |
| :--- | :--- | :--- | :--- |
| **Linear Regression** | £213,800.02 | £160,517.79 | 0.943 |
| **Random Forest** | £188,185.32 | £144,164.48 | 0.955 |
| **XGBoost Regressor** | **£89,175.28** | **£58,545.99** | **0.990** |

### 3. Feature Importances (XGBoost / Random Forest)
* **XGBoost** significantly outperformed the baseline models, achieving an exceptional **R² score of 0.990**, which implies it explains 99% of the variance in London house prices.
* Based on feature importance metrics, **Square Meters** (property size) emerged as the single most dominant driver of property value, followed by specific luxury materials and prime neighborhoods.

![Feature Importances](feature_importance.png) *(Save your feature importance plot as feature_importance.png and place it in the root folder)*

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python 3.12+
* **Data Manipulation:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib`, `seaborn`
* **Machine Learning:** `scikit-learn`, `xgboost`

---

## 💻 Getting Started

### Prerequisites
Make sure you have Python installed, then set up the required libraries:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
```

### Installation & Execution
1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com
   cd London_House
   ```
2. Open and run the Jupyter Notebook file to execute the pipeline:
   ```bash
   jupyter notebook london-house-price-prediction.ipynb
   ```
