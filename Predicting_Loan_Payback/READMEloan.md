[Loan Default Prediction with XGBoost Classifier](./img1.png)
---

# Loan Default Prediction with XGBoost

## 📌 Project Overview

This project predicts whether a borrower will pay back a loan based on historical loan and borrower data. We use **XGBoost**, a high-performance gradient boosting algorithm, to train the model and generate predictions.

---

## 🗂️ Dataset

* **Training data**: Includes features such as income, credit score, loan amount, employment status, and other borrower-related attributes, along with the target variable `loan_paid_back`.
* **Test data**: Contains the same features but without the target variable.
* **ID column**: For test data, the IDs start at `593994`.

---

## 🛠️ Data Preprocessing

* **Numerical features**: Imputed missing values with median and scaled using `StandardScaler`.
* **Categorical features**: Imputed missing values with most frequent value and one-hot encoded.
* **Pipeline**: Preprocessing and XGBoost model combined into a `Pipeline` for reproducibility and cleaner workflow.

---

## ⚙️ Model

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

**Validation ROC-AUC**: 0.921

---

## 📊 Feature Importance

* Plotted top 20 most important features.
* Features are colored based on importance intensity using Matplotlib colormaps (`viridis`, `plasma`, etc.).
* Feature importance helps understand which features contribute most to predictions.

---

## 💻 Usage

1. **Train the model**

```python
random_search.fit(X_train, y_train)
best_model = random_search.best_estimator_
```

2. **Predict on test set**

```python
y_test_proba = best_model.predict_proba(test)[:, 1]
submission = pd.DataFrame({
    'id': range(593994, 593994 + test.shape[0]),
    'loan_paid_back': y_test_proba
})
submission.to_csv('xgboost_test_predictions.csv', index=False)
```

---

## 📈 Results

* Model performs well on validation set with ROC-AUC ~0.92.
* Top features influencing predictions include credit score, debt-to-income ratio, annual income, and loan amount.

---

## ⚡ Notes

* RandomizedSearchCV was used due to the large dataset (~500k rows), which speeds up hyperparameter tuning compared to GridSearchCV.
* Early stopping and proper CV folds were considered to prevent overfitting.
* Submission CSV includes **probability of paying back loan** as required.

---

I can also make a **shorter, more “GitHub-friendly” version** with badges, installation instructions, and quick usage snippet if you want.

Do you want me to do that version too?
