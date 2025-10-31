# 🏆 Kaggle Machine Learning Competitions Folder 

Welcome to my collection of **Kaggle competition projects**!


This repository showcases my code, experiments, and final scores from various machine learning challenges I’ve participated in. 

Each folder corresponds to a specific competition.

---
## 📂 Repository Structure
My workflow typically includes:

1. EDA  
   - Visualizations with plotly, matplotlib, seaborn to detect outliers or unreasonable values (ex. age is 200)
 
2. Feature Engineering / Dimension Reduction / Removing influence of unimportant features  
   - Create new features if necessary (to reduce dimensionality!)  
   - Feature importance selection with L1 Lasso Linear Regression or Tree Based Models.  
     - Lasso : These select the most important features, shrink coefficients of unimportant features with a penalty to zero.  
     - Tree : Rank feature importance and select top ones only (tree)  
   - Dimensionality reduction methods (PCA, t-SNE, LDA if there are too many variables)  
     - These create new features by combining old ones.  

3. Data Preprocessing  
   - Imputation of missing values  
   - StandardScaler for numerical variables  
   - Onehotencoding for Categorical Variables  
   - Pipelines : ColumnTransformer (preprocessor for cat and num variables)  

4. Model selection based on evaluation metrics  

5. Model hyperparameter tuning  
   - GridSearchCV, RandomSearchCV, etc.  

6. Validation results after hyperparameter tuning, submissions & final score (+ metric used)  
   - Sometimes a generic model offers greater accuracy for unseen data!  

<p align="right">
  <img src="./img1.png" alt="Model Simplicity vs Complexity" width="400">
</p>



---

## 📈 Competitions & Scores

| Competition                                                                                                          | Model Deployed                            | Best Score & Metric Used     | Rank    | Notebook                                         |
| -------------------------------------------------------------------------------------------------------------------- | ------------------------------------- | --------------- | ------- | ------------------------------------------------ |
| [Predicting Road Accident Risk](https://www.kaggle.com/competitions/playground-series-s5e10/overview)                                          | Classic binary classification starter | **0.00569 [RMSE](https://www.geeksforgeeks.org/r-language/root-mean-square-error-in-r-programming/)**       | Top 5%  | [Notebook](./titanic/notebooks/final.ipynb)      |
| [House Prices: Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques) | Predict house prices                  | **0.118 RMSLE** | Top 10% | [Notebook](./house-prices/notebooks/final.ipynb) |
| [Tabular Playground Series – Feb 2022](https://www.kaggle.com/competitions/tabular-playground-series-feb-2022)       | Tabular regression challenge          | **0.842 RMSE**  | Top 8%  | [Notebook](./tps-feb-2022/notebooks/final.ipynb) |

*(I'm adding my actual scores and links as I go!)*

---

## 💡 Goals

This repository serves as:

* A **learning diary** of my Kaggle journey
* A **reference library** for common ML pipelines for reproducibility
* A **showcase** of my applied ML skills

---

## 📬 Contact

If you’d like to see more of my work or discuss ML approaches, feel free to reach out!

* 🧑‍💻 [Portfolio Website](https://jayelle0609.github.io/jialing/)
* 🧑‍💻 [Tableau Viz](https://public.tableau.com/app/profile/jialingteo/vizzes)
* ✉️ [jayelleteo@gmail.com](mailto:jayelleteo@gmail.com)
* 🐦 [Resume](https://drive.google.com/file/d/1Rq7kx1UOF96GE26drsnB5flgt6iCxdYP/view?usp=sharing) | 💼 [LinkedIn](https://linkedin.com/in/jialingteo)

---

⭐ **Thank you for viewing my work!**
