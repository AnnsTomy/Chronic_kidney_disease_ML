# **A Comparative Study of Machine Learning Models on Chronic Kidney Disease**

## **Table of Contents**
1. [Project Overview](#project-overview)  
2. [Objectives](#objectives)  
3. [Research Question](#research-question)  
4. [Exploratory Data Analysis](#exploratory-data-analysis)  
5. [Data Preprocessing](#data-preprocessing)  
6. [Methodology](#methodology)  
7. [Model Performance](#model-performance)  
8. [Feature Importance](#feature-importance)  
9. [Limitations](#limitations)    
10. [License](#license)  



## **PROJECT OVERVIEW**
---

Chronic Kidney Disease (CKD) is a significant public health issue characterized by various clinical signs and symptoms. Early diagnosis and effective treatment are crucial for improving patient outcomes.  **Random Forest**, **XGBoost**, and **Support Vector Machines (SVM)** are machine learning models used in this research to analyse clinical and demographic data, compare model performances, find important diagnostic features, and optimise parameters to attain high predictive accuracy.

Utilising information from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/chronic_kidney_disease), the study demonstrates how predictive healthcare may be used to create trustworthy diagnostic tools. The top-performing model is identified using performance indicators including **accuracy**, **F1-score**, **precision**, and **recall**.

---
## **Objectives**

1. Evaluate the effectiveness of machine learning models (**Random Forest**, **XGBoost**, and **SVM**) for predicting CKD.  
2. Identify critical clinical and demographic features essential for diagnosing CKD.  
3. Improve model performance through hyperparameter optimization.  
4. Address dataset and model limitations for a balanced evaluation.

---

## **Research Question**

How do different machine learning models compare in their effectiveness for predicting Chronic Kidney Disease based on clinical and demographic features?

---

## **Exploratory Data Analysis**

Key insights from EDA:  
- Data includes both **numerical** and **categorical** features with significant missing values requiring preprocessing.  
- Numerical variables (e.g., **blood pressure**, **serum creatinine**) exhibit skewed distributions.  
- Categorical variables (e.g., **red blood cells**, **pus cells**, **diabetes**) are strongly associated with CKD.  
- Class imbalance addressed using **SMOTE**.  
- **Correlation analysis** found highly correlated **hemoglobin**, **pcv** and **rbcc**. So I kept **hemo** which is clinically vital and dropped others.

Visualizations such as histograms, heatmaps, and box plots aided in identifying feature importance and distribution patterns.

---

## **Data Preprocessing**

- **Normalization**: Applied Standard Scaler to normalize numerical features.  
- **Imputation**: Replaced missing values with mean (numerical) and mode (categorical).  
- **Encoding**: Binary categorical variable encoded (e.g., `ckd=1`, `notckd=0`).  
- **Class Imbalance**: Resolved using **SMOTE**.  
- **Feature Selection**: Retained clinically relevant features like **hemoglobin** and dropped **pcv** and **rbcc**.   
- **Dataset Split**: Divided into training and testing sets (80:20 ratio).  

---

## **Methodology**

Three machine learning models were implemented:  

1. **Random Forest (RF)**:  
   - Combines decision trees using bagging and random feature selection.  
   - Tuned parameters: `n_estimators`, `max_depth`, `min_samples_split`, 'min_samples_leaf', 'random_state'.  
   - Achieved **96.25% accuracy**.  

2. **Support Vector Machine (SVM)**:  
   - Utilized the RBF kernel for non-linear feature interactions.  
   - Tuned parameters: `gamma`, `probability`, `max_iter`.  
   - Achieved **93.75% accuracy**.  

3. **XGBoost**:  
   - Gradient-boosted tree algorithm.  
   - Tuned parameters: `max_depth`, `learning_rate`, `n_estimators`, `subsample`, 'random_state', 'use_label_encoder=True',
                             'eval_metric='logloss''.  
   - Achieved **98.75% accuracy**.  

---

## **Model Performance**

| Model                  | Accuracy | Precision (CKD) | Recall (CKD) | F1-Score (CKD) |
|------------------------|----------|-----------------|--------------|----------------|
| **Random Forest**      | 96.25%   | 96%             | 98%          | 97%            |
| **Support Vector Machine** | 93.75%   | 91%             | 100%         | 95%            |
| **XGBoost**            | 98.75%   | 100%            | 98%          | 99%            |

---

### Detailed Metrics
| Metric                     | Random Forest | SVM    | XGBoost |
|----------------------------|---------------|--------|---------|
| **Accuracy**               | 0.9625        | 0.9375 | 0.9875  |
| **Precision (Class 0)**    | 0.96          | 1.00   | 0.97    |
| **Recall (Class 0)**       | 0.93          | 0.82   | 1.00    |
| **F1-score (Class 0)**     | 0.95          | 0.90   | 0.98    |
| **Precision (Class 1)**    | 0.96          | 0.91   | 1.00    |
| **Recall (Class 1)**       | 0.98          | 1.00   | 0.98    |
| **F1-score (Class 1)**     | 0.97          | 0.95   | 0.99    |
| **Macro Avg Precision**    | 0.96          | 0.96   | 0.98    |
| **Macro Avg Recall**       | 0.95          | 0.91   | 0.99    |
| **Macro Avg F1-score**     | 0.96          | 0.93   | 0.99    |
| **Weighted Avg Precision** | 0.96          | 0.94   | 0.99    |
| **Weighted Avg Recall**    | 0.96          | 0.94   | 0.99    |
| **Weighted Avg F1-score**  | 0.96          | 0.94   | 0.99    |

---

## **Feature Importance**

Top features identified across models:  
- **Hemoglobin (Hemo)**: Key indicator of oxygen transport and kidney health.  
- **Specific Gravity (SG)**: Reflects urine concentration.  
- **Serum Creatinine (SC)**: Marker for kidney filtration efficiency.  
- **Albumin (Al)**: Indicates kidney damage.  

---

## **Limitations**

1. **Small Dataset Size**: Reduces generalizability.  
2. **Synthetic Data (SMOTE)**: May not fully replicate real-world complexities.  
3. **Demographic Features**: Absence of factors like gender impacts diversity in predictions.

---




