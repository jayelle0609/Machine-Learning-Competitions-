![exercise](img.png)
# Model Comparison and Selection

This project explores regression models for predicting exercise calorie expenditure based on given character demographics.

---

**🚀 Final Model RMSLE:** 0.05903 

---

## Initial CV Results (on Sample)

| Model             | RMSE Mean | R² Mean | RMSE Std | R² Std  |
| ----------------- | --------- | ------- | -------- | ------- |
| XGBoost           | 3.76      | 0.996   | 0.022    | 0.00004 |
| Random Forest     | 3.87      | 0.996   | 0.038    | 0.00008 |
| Gradient Boosting | 4.70      | 0.994   | 0.010    | 0.00002 |
| Linear Regression | 11.10     | 0.968   | 0.025    | 0.00013 |
| Ridge Regression  | 11.10     | 0.968   | 0.025    | 0.00013 |
| Lasso Regression  | 11.13     | 0.968   | 0.023    | 0.00012 |

> 5-fold cross-validation was used to ensure reliable performance estimates.

## Final Model Performance

| Model                        | Validation RMSE | Validation MAE | Validation R2 Score |
| ---------------------------- | --------------- | -------------- | ------------------- |
| Before Hyperparameter Tuning | 3.73            | 2.29           | 1.00                |
| After Hyperparameter Tuning  | 3.59            | 2.15           | 1.00                |

## Why XGBoost Was Selected

* **High predictive accuracy**: Outperformed all other models in initial CV and after tuning.
* **Handles non-linear relationships** effectively.
* **Built-in regularization** reduces overfitting.
* **Fast and flexible** for large datasets and hyperparameter tuning.

