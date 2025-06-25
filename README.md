# 🧠 Census Income Prediction using Random Forest

## 📌 Problem Statement

This project analyzes census income data to predict whether an individual's **annual income exceeds $50K** based on demographic and employment-related features. The model is built using a **Random Forest Classifier**.

---

## 📊 Dataset Description

The data comes from the **1994 US Census Bureau** database. It contains **~32,000 records** and 15+ features.

| Column Name        | Description                             |
|--------------------|-----------------------------------------|
| age                | Age of the individual                   |
| workclass          | Type of employer                        |
| fnlwgt             | Final weight                            |
| education          | Education level                         |
| education-num      | Years of education                      |
| marital-status     | Marital status                          |
| occupation         | Occupation                              |
| relationship       | Family relationship                     |
| race               | Ethnicity                               |
| sex                | Gender                                  |
| capital-gain       | Capital gain                            |
| capital-loss       | Capital loss                            |
| hours-per-week     | Weekly working hours                    |
| native-country     | Country of origin                       |
| Annual-Income      | Target variable (`>50K` or `<=50K`)     |

---

## 🧹 Preprocessing Steps

- Replaced `?` placeholders with `NaN`
- Imputed missing values using **mode**
- One-hot encoded categorical variables
- Renamed the target column to `Annual_Income`
- Performed outlier and correlation checks
- Split data into train (80%) and test (20%)

---

## 🤖 Model Used

> **RandomForestClassifier** from `sklearn.ensemble`

```python
from sklearn.ensemble import RandomForestClassifier
rf = RandomForestClassifier(random_state=42)
rf.fit(X_train, y_train)
