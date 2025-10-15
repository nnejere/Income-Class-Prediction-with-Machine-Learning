# 🏆 Income Prediction Using Machine Learning  

## 📊 Dataset Information  
- **Source:** [UCI Machine Learning Repository – Adult Dataset](https://archive.ics.uci.edu/ml/datasets/adult)  
- **Description:** This dataset contains demographic and employment-related attributes for ~48,000 individuals from the 1994 U.S. Census. The target variable is income: whether a person earns more than \$50K per year. The project is a complete Machine Learning workflow covering dataset exploration, cleaning, analysis, preprocessing and building and evaluating both baseline and carefully tuned models.  

---

## 🎯 Problem Statement 
Predicting income levels based on demographic and employment features can help reveal patterns in socioeconomic factors and support better decision-making in areas such as policy, marketing, and financial services. This project aims to develop a machine learning model that not only performs well overall but also excels at correctly identifying individuals earning more than $50K per year which is a minority class in the dataset. This requires a balanced approach that improves recall and roc_auc for high-income earners without significantly compromising precision or overall model accuracy.  

---

## 📝 Objectives  
- Build a machine learning model capable of accurately predicting whether an individual earns **> \$50K annually**.  
- Understand key demographic and employment factors that influence income levels.  
- Compare baseline and tuned versions of multiple algorithms to evaluate trade-offs between precision and recall.  
- Establish a reusable pipeline for data cleaning, preprocessing, modeling, and evaluation.  

---

## ⚙️ Methods and Approach  

### 🔹 Data Preparation & Feature Engineering  
- Cleaned missing values and grouped sparse categorical variables.  
- Addressed outliers (e.g., capped hours-per-week).  
- Applied encoding for categorical features and scaling where appropriate.  
- Created a full preprocessing pipeline for reproducibility and deployment.  

### 🔹 Exploratory Data Analysis (EDA)  
Key findings:  
- **Education & Age:** Higher education and older age groups strongly correlate with higher income.  
- **Marital Status & Sector:** Married individuals with a present spouse and those in private/government sectors were more likely to earn >\$50K.  
- **Class Imbalance:** Variables like sex, race, and native_country were imbalanced but revealed important underlying patterns and biases.  

### 🔹 Modeling  
- Built **four models** in both baseline and tuned forms: Logistic Regression, Random Forest, XGBoost, and SVM.  
- Applied **hyperparameter tuning** and **class imbalance handling** (e.g., `class_weight='balanced'`, `scale_pos_weight`).  
- Saved all models and the preprocessing pipeline for reproducibility and future deployment.  

---

## 📈 Key Results  

| Model | Accuracy (Tuned) | Recall (Tuned) | Precision (Tuned) | ROC AUC (Tuned) |
|-------|-----------------|---------------|----------------|----------------|
| **XGBoost** | **0.837** | **0.874** | **0.623** | **0.930** |
| Random Forest | 0.830 | 0.848 | 0.615 | 0.916 |
| SVM | 0.807 | 0.865 | 0.574 | 0.905 |
| Logistic Regression | 0.801 | 0.843 | 0.567 | 0.894 |




- **XGBoost** achieved the **highest recall and ROC AUC**, making it the best at identifying high-income individuals.  
- Trade-offs between precision and recall were carefully managed; improving recall for the >\$50K class required accepting slightly lower precision.  

---

## 🚀 Recommendations for Future Work  
- **Collecting more Balanced Data:** Getting more data for the minority class
- **SMOTE / Oversampling:** Further address class imbalance by generating synthetic samples of the minority class.  
- **Feature Selection & Engineering:** Explore new derived features and remove less informative ones to reduce noise.  
- **Model Stacking:** Combine multiple tuned models (stacking or blending) to improve robustness.  
- **Explainability Tools (e.g., SHAP):** Provide deeper feature importance at the individual prediction level to improve trust and transparency.  

---

## 🏁 Conclusion  
This project demonstrates the value of a structured ML workflow — from data cleaning, EDA, and preprocessing to modeling and evaluation. It provides a strong, extensible framework for income prediction and similar real-world classification tasks while highlighting the importance of balancing performance with fairness and interpretability.  

