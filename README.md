
# 🍽️ Restaurant Tips Analysis – Excel Regression Project

This repository contains a complete Excel-based data analytics project focused on predicting restaurant tips based on various customer and transaction attributes. The dataset is derived from restaurant transactions and includes features such as total bill, party size, gender, day, time, and smoking status.

---

## 📊 Project Objective

To build a regression model using Excel to predict the amount of tip a customer would give based on the available features, and evaluate the performance of the model using RMSE.

---

## 📁 Dataset Description

The dataset includes the following columns:

| Column        | Description                                  |
|---------------|----------------------------------------------|
| `total_bill`  | Total bill amount in dollars                 |
| `tip`         | Tip given by the customer                    |
| `sex`         | Gender of the customer (Male/Female)         |
| `smoker`      | Whether the customer is a smoker (Yes/No)    |
| `day`         | Day of the week (Thur, Fri, Sat, Sun)        |
| `time`        | Time of day (Lunch/Dinner)                   |
| `size`        | Size of the dining party                     |

---

## 🛠️ Project Steps

### 1. Data Cleaning
- Removed missing values
- Removed duplicate records using Excel built-in tools

### 2. Feature Engineering
- Encoded categorical variables using `IF` statements:
  - Gender → `Sex_numeric` (Male: 1, Female: 0)
  - Smoker → `Smoker2` (Yes: 1, No: 0)
  - Day → `Day2` (Thur: 1, Fri: 2, Sat: 3, Sun: 4)
  - Time → `Time2` (Lunch: 0, Dinner: 1)

### 3. Correlation Analysis
- Used Excel `CORREL()` function to determine the correlation of each independent variable with the `tip`.

### 4. Regression Modeling
- Applied **Excel Data Analysis Toolpak > Regression** to build the model.
- Used independent variables: `total_bill`, `size`, `Sex_numeric`, `Smoker2`, `Day2`, `Time2`.
- Extracted model coefficients and calculated predicted tips using Excel formulas.

### 5. Model Evaluation
- Predicted Tip = Intercept + (Coeff1 × `total_bill`) + ... + (CoeffN × `Time2`)
- Calculated **RMSE** (Root Mean Squared Error) to evaluate model accuracy:
  ```excel
  =SQRT(AVERAGE((Actual - Predicted)^2))
