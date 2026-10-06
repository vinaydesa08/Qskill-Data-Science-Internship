# 🏠 House Price Prediction

## 📌 Project Overview

This project focuses on predicting house prices using machine learning techniques. The project uses housing data containing property characteristics, demographic information, income information, and ocean proximity.

The target variable is `median_house_value`. Two regression models, Linear Regression and Random Forest Regression, were developed and evaluated to predict house values.

---

## 🎯 Problem Statement

House prices depend on several factors such as location, income level, housing age, number of rooms, population, and proximity to the ocean.

The objective of this project is to analyze these factors and build a machine learning model that can predict the median value of houses based on the available features.

---

## 🎯 Objectives

- Load and understand the housing dataset.
- Perform data cleaning and preprocessing.
- Handle missing values.
- Perform exploratory data analysis (EDA).
- Analyze relationships between features and house values.
- Encode categorical variables.
- Split the dataset into training and testing sets.
- Build a Linear Regression model.
- Build a Random Forest Regression model.
- Evaluate both models using MAE, RMSE, and R².
- Analyze feature importance.
- Visualize actual and predicted house values.
- Save the prediction results for further analysis.

---

## 📊 Dataset Information

The dataset contains **20,640 records and 10 columns**.

### Dataset Features

| Feature | Description |
|---|---|
| `longitude` | Geographic longitude of the housing location |
| `latitude` | Geographic latitude of the housing location |
| `housing_median_age` | Median age of houses in the area |
| `total_rooms` | Total number of rooms |
| `total_bedrooms` | Total number of bedrooms |
| `population` | Population in the area |
| `households` | Number of households |
| `median_income` | Median income of households |
| `median_house_value` | Median house value - Target variable |
| `ocean_proximity` | Categorical information about proximity to the ocean |

### Target Variable

```text
median_house_value