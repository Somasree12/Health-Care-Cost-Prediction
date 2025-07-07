🩺💰 **Predicting Annual Healthcare Costs Using Machine Learning**

 **📄 Introduction**
 
Healthcare costs are rising globally at a rapid pace, and predicting patient costs accurately can help **insurance companies**, **healthcare providers**, and **policymakers** design better programs and optimize resources. In this project, we have built a machine learning pipeline to predict annual healthcare costs using patient data such as **age, BMI, smoking status, and chronic conditions**. We explored different models like **linear regression, random forest regression(default), random forest regression (using grid search hyperparameter)**, compared their performance, and gained insights into the factors that drive higher costs.

---
 🔎 **Data Overview**
 
The dataset used in this project ("healthcare_costs.csv") includes 50 patients and the following columns:
- PatientID: Unique identifier
- Age: Age of the patient
- BMI: Body Mass Index
- SmokingStatus: Smoker or Non-Smoker
- ChronicCondition: Presence of chronic health conditions
- AnnualCost: Annual healthcare expenditure (target variable)
---
🛠 **Exploratory Data Analysis**

🗺 Distribution of Key Features:
- Age and BMI showed a wide spread, with most patients in middle-to-older age groups and BMI around 30.
- AnnualCost distribution was slightly right-skewed, with some high-cost outliers.
- SmokingStatus: 29 smokers, 21 non-smokers.
- ChronicCondition: More than half had chronic conditions.
 💡 Correlations:
The heatmap revealed a moderate correlation between age, BMI, and annual costs. Smoking and chronic conditions appeared to contribute to higher costs, as seen in box plots.
---
 ⚙️**Preprocessing**
 
- Encoding: Converted `SmokingStatus` and `ChronicCondition` to binary (0/1).
- Dropped: PatientID (non-predictive).
- Scaling: Standardized numeric features to ensure models are trained properly.
- Cost binning: Created cost bins for stratified train-test splitting, ensuring balanced representation of high and low-cost patients.
 ---
 🤖**Modeling**
 
 1️⃣ **Linear Regression**
As a baseline model:
- MAE: 1,702
- MSE:4394722    
- RMSE: 2,096
- R²: -0.03
The negative R² indicated the model was underfitting — unable to capture nonlinear interactions.

 2️⃣**Random Forest Regressor (Default)**
Switched to a nonlinear ensemble model:
- MAE: 1,572
- MSE: 3903817 
- RMSE: 1,975
- R²: 0.09
Slight improvement, but still room for tuning.

  3️⃣ **Random Forest (Tuned with Grid Search)**
  
Performed hyperparameter tuning using GridSearchCV:
- Best parameters:
  - n_estimators: 50
  - max_depth: None
  - min_samples_split: 10
  - min_samples_leaf: 4
- MAE: 1,552
- MSE: 3263494
- RMSE: 1,807
- R²: 0.24
 ---
   💥 **Model Comparison**

| Model                | MAE   |  MSE   | RMSE  |   R²  |
|----------------------|-------|------- |------ |-------| 
| Linear Regression    | 1,702 |4.394722 |2,096 | -0.03 |
| Random Forest Default| 1,572 |3.903817 |1,975 | 0.09  |
| Random ForestTuned   | 1,552 |3.263494 |1,807 | 0.24  |

The tuned random forest performed best, reducing errors and improving explained variance.

---
💡 **Insights**

- **Age** and **BMI** were the most important features contributing to cost predictions.
- **Smoking** and **chronic conditions** had significant effects on higher healthcare expenses, consistent with known medical trends.
- Ensemble methods like Random Forest performed significantly better than linear models, indicating complex nonlinear relationships in the data.---

---

📈 **Visualizations**

🎯 [Univariate Logo Plots](https://github.com/Somasree12/Health-Care-Cost-Prediction/blob/main/Univariate.png)

💥 [Bivariate Logo Plots](https://github.com/Somasree12/Health-Care-Cost-Prediction/blob/main/Bivariate.jpg)

🔥 [Correlation Heatmap](https://github.com/Somasree12/Health-Care-Cost-Prediction/blob/main/Correlation%20Heatmap.png)

🔥 [Feature Importance](https://github.com/Somasree12/Health-Care-Cost-Prediction/blob/main/Feature%20Importance.png)

🎯[ Actual vs Predicted Costs](https://github.com/Somasree12/Health-Care-Cost-Prediction/blob/main/Actual%20vs%20Predic.png)

📊 [R² Score Comparison](https://github.com/Somasree12/Health-Care-Cost-Prediction/blob/main/R2%20Compare.png)


---
 ✅ **Conclusion**
 
This project demonstrated the power of machine learning to model healthcare costs, even on a small dataset. With larger data and additional features (like medical history or region), predictive performance could further improve.

---
💬**Future Work**

- Use advanced models like XGBoost or CatBoost.
- Include additional features: hospital visits, medications, lab results.
- Apply model explainability tools (e.g., SHAP) to interpret individual predictions.
---

 💻 **Code & Resources**
 
- [GitHub Repository Link]( https://github.com/Somasree12/Health-Care-Cost-Prediction/blob/main/health_care.ipynb)
- Python, pandas, scikit-learn, seaborn, matplotlib

---
