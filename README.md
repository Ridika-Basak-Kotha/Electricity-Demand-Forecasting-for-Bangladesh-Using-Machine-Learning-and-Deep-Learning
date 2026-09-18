# bangladesh-electricity-demand-forecasting-using-machine-learning
# ⚡ Bangladesh Electricity Demand Forecasting Using Machine Learning

### Short-Term Electricity Demand Forecasting Using Historical Electricity Demand and Time-Series Features

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)]()
[![XGBoost](https://img.shields.io/badge/XGBoost-Machine%20Learning-red.svg)]()
[![TensorFlow](https://img.shields.io/badge/TensorFlow-Deep%20Learning-orange.svg)]()
[![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow.svg)]()

---

## 📌 Project Overview

This project investigates machine learning approaches for electricity demand forecasting in Bangladesh.

The objective is to learn historical electricity demand patterns and develop predictive models that can estimate future electricity demand.

The current implementation focuses on historical electricity demand and time-based features, with weather-enhanced forecasting planned as an extension.

---

## 🎯 Objectives

* Analyze historical electricity demand patterns in Bangladesh.
* Perform exploratory data analysis.
* Engineer time-based and lag features.
* Apply chronological train-validation-test splitting.
* Train and compare multiple machine learning models.
* Evaluate forecasting performance using standard regression metrics.
* Investigate factors associated with electricity demand patterns.
* Extend the system toward weather-aware short-term forecasting.

---

## 📊 Dataset

The primary dataset used in this project is:

**Hourly Electricity Generation, Demand, Load Shedding, and Fuel Mix Dataset for Bangladesh (2015–2026)**

Source:

https://data.mendeley.com/datasets/vpk8spw2mm/1

Additional datasets considered for future/weather-enhanced experiments:

* Load Forecasting Dataset — Kaggle
* Household Power Consumption Dataset — Kaggle
* Bangladesh Weather Dataset — Kaggle

Dataset links and details are available in `data/README.md`.

---

## 🧹 Data Processing

The electricity dataset is converted into a chronological time-series format.

The preprocessing and feature engineering pipeline includes:

* Datetime conversion
* Chronological sorting
* Removal of unnecessary variables
* Hour extraction
* Month extraction
* Year extraction
* Day/evening/night indicators
* Weekend/weekday indicators
* Seasonal features
* Historical demand lag features

---

## ⏰ Time-Based Features

The current model uses features such as:

* Hour
* Month
* Year
* Day peak indicator
* Evening peak indicator
* Night indicator
* Weekend indicator
* Weekday indicator
* Seasonal indicators
* Previous-hour demand
* Previous-week demand

---

## 🔄 Train / Validation / Test Strategy

Because electricity demand is time-dependent, a chronological split is used instead of a random train-test split.

```text
2015 ───────── 2020 | 2021 ─── 2022 | 2023 ───────── 2026
       TRAIN        |   VALIDATION   |       TEST
```

This approach helps preserve the temporal ordering of observations and reduces the risk of using future observations during training.

---

## 🤖 Models

The current implementation compares five models:

### 1. Linear Regression

Used as a simple baseline model.

### 2. Random Forest

An ensemble tree-based regression model used to capture nonlinear relationships.

### 3. XGBoost

A gradient boosting model used for nonlinear demand prediction.

### 4. Multi-Layer Perceptron (MLP)

A feed-forward neural network for learning nonlinear relationships among the engineered features.

### 5. Recurrent Neural Network (RNN)

A neural network architecture investigated for sequential electricity demand modeling.

---

## 📏 Evaluation Metrics

The models are evaluated using:

* RMSE
* MAE
* R² Score

The validation and test results are stored in:

```text
results/model_comparison.csv
```

---

## 📈 Results

The final model comparison is presented in:

```text
results/model_comparison.csv
```

Visualizations include:

* Actual vs Predicted Demand
* Forecast plots
* Feature importance
* Model performance comparison

Results shown in this repository are based on the actual experiments performed in the project notebook.

---

## 🌦️ Planned Weather-Enhanced Forecasting

A future stage of the project will integrate Bangladesh weather information with historical electricity demand.

The intended feature set includes variables such as:

* Temperature
* Humidity
* Rainfall
* Wind speed
* Atmospheric pressure

The purpose of this extension is to investigate whether weather information provides additional predictive value beyond historical demand and temporal features.

---

## 🔮 Future Work

Future development will focus on:

* Weather-demand dataset integration
* 1-hour-ahead forecasting
* 1-day-ahead forecasting
* 1-week-ahead forecasting
* Improved lag and rolling features
* Hyperparameter optimization
* LSTM/GRU-based forecasting
* Transformer-based time-series forecasting
* SHAP-based model explainability
* Real-time forecasting dashboard
* Model deployment through an API

---

## 🗂️ Repository Structure

```text
bangladesh-electricity-demand-forecasting/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── Bangladesh_Electricity_Demand_Forecasting.ipynb
│
├── data/
│   └── README.md
│
├── results/
│   ├── model_comparison.csv
│   ├── actual_vs_predicted.png
│   ├── demand_forecast.png
│   └── feature_importance.png
│
└── reports/
    └── project_report.pdf
```

---

## 📓 Google Colab

The complete experimental notebook can be accessed through Google Colab:

**[Open Google Colab Notebook](YOUR_COLAB_LINK_HERE)**

---

## 📄 Project Report

The detailed project report is available in:

```text
reports/project_report.pdf
```

---

## 🛠️ Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* TensorFlow / Keras
* Matplotlib
* Seaborn
* Google Colab
* Jupyter Notebook

---

## 👩‍💻 Author

**Ridika Basak**

Computer Science & Engineering
BRAC University

---

## 📌 Project Status

**Current stage:** Machine learning-based electricity demand forecasting using historical demand and temporal features.

**Next stage:** Weather-integrated multi-horizon forecasting for 1-hour, 1-day, and 1-week prediction.
