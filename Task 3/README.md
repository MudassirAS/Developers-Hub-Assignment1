# 🧠 Task 3 – Customer Churn Prediction (Bank Customers)

**Submitted by:** Mudassir Ahmed Shaikh  
**Organization:** Developer's Hub Corporation  
**Assignment:** Internship Task 3 – Predicting Customer Churn in a Bank

---

## 🎯 Objective

The goal of this task was to build a machine learning model that can accurately predict whether a customer will **exit (churn)** from the bank based on their account activity and profile data.

---

## 📂 Dataset Overview

- Filename: `Churn_Modelling.csv`
- Total Records: `10,000`
- Total Features: `14` (including target)

**Target column:** `Exited`  
> `1` = Customer exited (churned)  
> `0` = Customer stayed

---

## 🛠️ Workflow Summary

### ✅ Clean and prepare the dataset
- Removed unnecessary columns: `RowNumber`, `CustomerId`, `Surname`
- Confirmed no missing values were present
- Checked data types and structure

### ✅ Encode categorical features such as geography and gender
- Used **One-Hot Encoding** for:
  - `Geography`: created `Geography_Germany`, `Geography_Spain`
  - `Gender`: created `Gender_Male`
- Used `drop_first=True` to avoid dummy variable trap

### ✅ Train a classification model
Trained and evaluated two models:
- **Logistic Regression**
- **Decision Tree Classifier**

All features were **scaled** using `StandardScaler` for logistic regression.

### ✅ Analyze feature importance to understand what influences churn
- Used `.feature_importances_` from the Decision Tree
- Visualized using a bar plot with seaborn

---

## 📊 Model Performance

### Logistic Regression (with scaled features)
- **Accuracy:** `81.4%`
- **Confusion Matrix:**
[[1547 60]
[ 312 81]]


### Decision Tree
- **Accuracy:** `78.05%`
- **Confusion Matrix:**
[[1362 245]
[ 194 199]]


---

## 🔍 Feature Importance (Decision Tree)

Top influencing features:
- `Age`
- `Balance`
- `EstimatedSalary`
- `CreditScore`
- `NumOfProducts`
- `IsActiveMember`

![Feature Importance Plot](feature_importance.png)

---

## 📈 Insights

- **Age** is the most significant factor affecting customer churn.
- Higher **Balance** and **EstimatedSalary** also correlate with higher churn probability.
- Customers from **Germany** and with low activity scores are more likely to leave.
- **Gender** had minimal influence on churn prediction.

---

## 📁 Files Included

- `Churn_Modelling.csv` – Dataset
- `Task3_Churn_Prediction.ipynb` – Main Jupyter notebook
- `README.md` – This file

---

