# Task 2 – Credit Risk Prediction

## 🔍 Objective

The objective of this task is to build a machine learning model that can predict whether a loan applicant is likely to default on a loan. This helps financial institutions in minimizing their risk and making informed lending decisions.

---

## 📂 Dataset

The dataset was acquired through kaggle (Link: https://www.kaggle.com/datasets/kmldas/loan-default-prediction)

The dataset contains information about individual loan applicants, including:
- **Employment status**
- **Bank balance**
- **Annual salary**
- **Defaulted?** (target variable: 1 = Defaulted, 0 = Not Defaulted)

Sample:
| Employed | Bank Balance | Annual Salary | Defaulted? |
|----------|---------------|----------------|-------------|
| 1        | 8754.36       | 532339.56      | 0           |
| 0        | 9806.16       | 145273.56      | 0           |

Total Records: 10000  
Target Type: Binary Classification (0 or 1)

---

## ⚙️ Approach

### 1. **Data Loading and Cleaning**
- The dataset was loaded using pandas.
- The `Index` column was dropped as it held no predictive value.
- Verified that there were **no missing values**.

### 2. **Exploratory Data Analysis (EDA)**
- Used **Seaborn** and **Matplotlib** to visualize relationships between features and default risk.
- Key visualizations:
  - Count plot of defaults
  - Box plots showing the distribution of `Bank Balance` and `Annual Salary` by default status

### 3. **Feature and Target Split**
- Features (`X`): All columns except `Defaulted?`
- Target (`y`): `Defaulted?`

Performed an 80-20 **train-test split** using `train_test_split()`.

---

## 🤖 Model Training

### Logistic Regression
- Trained using `sklearn.linear_model.LogisticRegression`
- Accuracy: **96.95%**
- Confusion Matrix:

[[1920 11]
[ 50 19]]



### Decision Tree Classifier
- Trained using `sklearn.tree.DecisionTreeClassifier`
- Accuracy: **95.3%**
- Confusion Matrix:

[[1885 46]
[ 48 21]]



---

## 📊 Evaluation Metrics

| Metric          | Logistic Regression | Decision Tree  |
|-----------------|---------------------|----------------|
| Accuracy        | 96.95%              | 95.3%          |
| True Positives  | 19                  | 21             |
| False Positives | 11                  | 46             |
| False Negatives | 50                  | 48             |

**Interpretation:**
- Logistic Regression performed slightly better overall.
- Decision Tree was slightly better at capturing actual defaulters (`TP = 21` vs `19`).

---

## 🧾 Conclusion

- Both models achieved high accuracy on the test set.
- Logistic Regression showed better precision with fewer false positives.
- Decision Tree captured more true defaulters, at the cost of more false positives.
- In real-world scenarios, **minimizing false negatives** (undetected defaulters) is often more important, so a tuned Decision Tree may be preferable.


---

## 📁 Files

- `Task2_Credit_Risk_Prediction.ipynb` — Jupyter notebook with full code and visualizations
- `data.csv` — Dataset used for training and testing
- `README.md` — Project summary and insights

---

## 📌 Dependencies

- Python 3.x
- pandas
- seaborn
- matplotlib
- scikit-learn

---

> Developed by Mudassir Ahmed Shaikh for Developers Hub Internship — Task 2  
> July 2025