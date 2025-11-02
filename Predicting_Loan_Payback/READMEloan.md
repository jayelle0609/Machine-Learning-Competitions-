<p align="center">
  <img src="img1.png" alt="header" width="600">
</p>

# Loan Default Prediction with XGBoost

## 📌 Project Overview

This project predicts whether a borrower will pay back a loan based on historical loan and borrower data. We use **XGBoost Classifer**, a high-performance gradient boosting algorithm, to train the model and generate predictions.

---

## 🗂️ Dataset

* **Training data**: Includes features such as income, credit score, loan amount, employment status, and other borrower-related attributes, along with the target variable `loan_paid_back`.


## 🛠️ Data Preprocessing

* **Numerical features**: Imputed missing values with median and scaled using `StandardScaler`.
* **Categorical features**: Imputed missing values with most frequent value and one-hot encoded.
* **Pipeline**: Preprocessing and XGBoost model combined into a `Pipeline` for reproducibility and cleaner workflow.
* **Classification Models tested** : Results below are scores on validation set.
  

| Model              | F1 Score | ROC-AUC | TN    | FP   | FN    | TP    |
| ------------------ | -------- | ------- | ----- | ---- | ----- | ----- |
| RandomForest       | 0.9406   | 0.9043  | 13901 | 9999 | 1763  | 93136 |
| LogisticRegression | 0.9107   | 0.9107  | 18381 | 5519 | 10944 | 83955 |
| GradientBoosting   | 0.9418   | 0.9149  | 14162 | 9738 | 1769  | 93130 |
| XGBoost            | **0.9423**   | **0.9196**  | 14441 | 9459 | 1928  | 92971 |

<img width="835" height="518" alt="image" src="https://github.com/user-attachments/assets/4adf90fc-0f85-4502-a003-a40552ae23e9" />

---

## ⚙️ Model Hyperparameter tuning

* **Algorithm**: XGBoost Classifier (`XGBClassifier`) with hyperparameter tuning using `RandomizedSearchCV`.
* **Hyperparameters tuned**:

  * `n_estimators`, `max_depth`, `learning_rate`, `subsample`, `colsample_bytree`, `min_child_weight`, `gamma`, `reg_alpha`, `reg_lambda`
* **Evaluation metric**: ROC-AUC score.

**Best parameters found:**

```text
{'subsample': 1.0, 'reg_lambda': 1.5, 'reg_alpha': 1, 'n_estimators': 500, 
 'min_child_weight': 3, 'max_depth': 3, 'learning_rate': 0.2, 'gamma': 0.1, 
 'colsample_bytree': 0.8}
```

**Validation ROC-AUC**: 0.92093

---

## 📊 Feature Importance

* Plotted top 10 most important features, contributing to prediction.
<img width="1189" height="790" alt="image" src="https://github.com/user-attachments/assets/bd7d997a-2d45-4415-9e2d-9ce5862de4ef" />


---

## 📈 Results

* Model performs well on test set, with a final score of **0.92142**.
* Hyperparameter tuning took 30 mins for over 500k rows of data.
<img width="721" height="114" alt="Screenshot 2025-11-02 at 9 08 33 AM" src="https://github.com/user-attachments/assets/c7f9afbe-9d3f-446e-96c6-f55e59408e5a" />


