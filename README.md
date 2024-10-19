# Walmart Sales Prediction

This project is designed to predict Walmart's weekly sales using machine learning techniques, including time series forecasting. This README provides an overview of the notebook structure and methodology used for the Walmart sales prediction.

## Table of Contents

1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Data](#data)
4. [Data Preprocessing](#data-preprocessing)
5. [Exploratory Data Analysis](#exploratory-data-analysis)
6. [Feature Engineering](#feature-engineering)
7. [Modeling](#modeling)
8. [Evaluation](#evaluation)
9. [Time Series Forecasting](#time-series-forecasting)
10. [Results](#results)
11. [Conclusion](#conclusion)

## Introduction

The goal of this project is to predict Walmart's weekly sales across various stores and departments using a combination of machine learning models and time series analysis. Key methods used include:
- Random Forest Regression for machine learning prediction.
- Auto ARIMA and Exponential Smoothing for time series forecasting.

## Requirements

The project requires the following libraries:
- Python 3.x
- Numpy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Statsmodels
- Pmdarima
- Google Colab (for running on cloud)

## Data

The project uses three datasets provided by Walmart:
- `stores.csv`: Information about different Walmart stores.
- `train.csv`: Training data containing sales information.
- `features.csv`: External features like fuel price, temperature, etc.

The dataset was preprocessed and cleaned to remove errors such as negative sales, missing values, and irrelevant columns.

## Data Preprocessing

Preprocessing steps include:
- Merging the `train.csv`, `stores.csv`, and `features.csv`.
- Handling missing values by filling null values with zeros.
- Removing erroneous rows (e.g., negative sales).
- Converting date columns to a proper datetime format.
- Encoding categorical variables such as `Store Type`, `IsHoliday`, and holiday information like Christmas, Super Bowl, etc.

## Exploratory Data Analysis

The following visualizations and analyses were performed:
- Sales trends based on holidays (Christmas, Thanksgiving, Super Bowl, Labor Day).
- Correlation analysis to explore interactions between variables like fuel prices, CPI, and unemployment.
- Boxplots and scatter plots to visualize weekly sales across different stores and departments.
- Pie charts for store type distribution.

## Feature Engineering

Features were engineered to improve model performance, such as:
- New columns for year, month, and week extracted from the date.
- Encoding of categorical variables like store types and holidays into numeric values.
- Dropping low-correlation features to simplify the model.

## Modeling

Multiple models were tested to predict the sales:
1. **Random Forest Regressor**: 
   - Trained on 70% of the data and evaluated on 30%.
   - Utilized `RobustScaler` and pipeline for scaling and fitting.
   - Hyperparameters like `n_estimators`, `max_depth`, `max_features` were tuned.
2. **Time Series Models**:
   - **Auto ARIMA**: Automatically tuned ARIMA for time series prediction.
   - **Exponential Smoothing**: Used Holt-Winters exponential smoothing to capture seasonality.

## Evaluation

The primary evaluation metric used was **Weighted Mean Absolute Error (WMAE)**, which gives higher weight to errors during holidays. Models were compared based on their WMAE performance.

- Random Forest Regressor: Achieved good accuracy with the tuned hyperparameters.
- Auto ARIMA and Exponential Smoothing were used to forecast sales using the time-series approach.

## Time Series Forecasting

The time-series analysis explored several techniques:
1. **Differencing**, **Shifting**, and **Log Transformation** to make the data stationary.
2. **Decomposing** the time series into trend, seasonality, and residual components.
3. **Auto ARIMA** for automated ARIMA forecasting.
4. **Exponential Smoothing** for additive trend and seasonality forecasting.

## Results

- The Random Forest model provided competitive results with a **WMAE** of ~1801.
- Time series models like Auto ARIMA and Exponential Smoothing were used for predicting future sales but did not outperform the Random Forest Regressor.

## Conclusion

The project demonstrates the use of machine learning models and time-series forecasting techniques for Walmart sales prediction. Random Forest emerged as a strong model for this task, while time-series models provided useful insights for long-term trends.

For future work, more advanced time-series models and deep learning techniques can be explored to improve accuracy further.

---

For any questions or suggestions, please feel free to open an issue or contribute to the project.
