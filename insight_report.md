# 📊 Insights Report: Census Income Prediction using Random Forest

## 📌 Objective

To develop a machine learning model using **Random Forest** to predict whether a person earns more than **$50K per year** based on demographic and employment-related attributes.

---

## 🔍 Data Insights

### 1. **Missing Values**
- Found placeholder `?` in `workclass`, `occupation`, and `native-country`.
- Replaced with **NaN** and imputed using **mode** (most frequent value).

### 2. **Data Preprocessing**
- Performed **one-hot encoding** for categorical variables.
- Checked for **outliers** and basic **correlation** among features.
- Renamed target column (`Annual-Income`) to `Annual_Income`.

---

## 🧠 Model Used

- **Model**: RandomForestClassifier
- **Train-Test Split**: 80:20
- **Random State**: 42

---

## 📈 Model Performance

| Metric         | Value     |
|----------------|-----------|
| Accuracy       | **85.83%** |
| Precision (>50K) | 0.74      |
| Recall (>50K)    | 0.63      |
| F1 Score (>50K)  | 0.68      |

### Confusion Matrix:
|               | Predicted ≤50K | Predicted >50K |
|---------------|----------------|----------------|
| **Actual ≤50K** |     4601      |      341       |
| **Actual >50K** |     582       |      989       |

---

## 🔥 Key Feature Importances

The top features influencing the model predictions:

| Rank | Feature                       | Importance |
|------|-------------------------------|------------|
| 1    | `capital-gain`               | 0.24       |
| 2    | `education-num`              | 0.15       |
| 3    | `hours-per-week`             | 0.13       |
| 4    | `age`                        | 0.12       |
| 5    | `marital-status_Married-civ-spouse` | 0.07 |

> 💡 **Capital gain** and **education level** play a major role in determining income level.

---

## 📉 Limitations

- Class imbalance: Higher proportion of `<=50K` earners affects recall for `>50K`.
- Some categorical variables have too many sparse categories (e.g., `native-country`).

---

## 🛠 Recommendations

- Try **class weighting** or **SMOTE** to improve recall for minority class.
- Tune hyperparameters like `n_estimators`, `max_depth`, and `min_samples_split`.
- Test advanced models like **XGBoost** or **LightGBM** for better performance.
- Feature engineering to combine and simplify sparse or related categorical values.

---

## ✅ Conclusion

The model is able to correctly predict income brackets with **high accuracy**. With better class balancing and model tuning, it can become a robust solution for income prediction based on census data.

