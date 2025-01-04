***A COMPARATIVE STUDY OF
MACHINE LEARNING MODELS
ON CHRONIC KIDNEY DISEASE***


PROJECT OVERVIEW

A worldwide public health issue, chronic kidney disease (CKD) has numerous clinical signs and complicated symptoms. Improving patient outcomes requires early diagnosis and efficient treatment. In order to diagnose CKD, this study analyses clinical and demographic data using machine learning models such as Random Forest, XGBoost, and Support Vector Machines (SVM). The research assesses these models' performances, finds key features for diagnosis, and adjusts model parameters for predicted accuracy using a dataset from the UCI Machine Learning Repository. The study highlights the expanding potential of predictive healthcare and aids in the creation of reliable diagnostic tools. Measures like as F1 score, accuracy, precision, and support are used to identify the top-performing model.

OBJECTIVES

The following are the project's main goals:

To assess the effectiveness of many machine learning models in predicting Chronic Kidney Disease (CKD), such as Random Forest, XGBoost, and Support Vector Machines (SVM).

To determine the essential clinical and demographic characteristics that are important for diagnosing chronic kidney disease.

To improve the efficacy and accuracy of the model by applying hyperparameter optimisation approaches.

To offer a fair assessment by looking at the dataset's and the models' limitations.

RESEARCH QUESTION

How do different machine learning models compare in their effectiveness for predicting Chronic Kidney Disease based on clinical and demographic features?

EXPLORATORY DATA ANALYSIS



The exploratory data analysis (EDA) of the Chronic Kidney Disease (CKD) dataset revealed a mix of numerical and categorical variables, with significant null values requiring preprocessing. Categorical variables, stored as 'object' types, were converted to numerical formats, while numerical variables, represented as 'float64', exhibited skewed distributions for features such as blood pressure, blood urea, serum creatinine, hemoglobin, and packed cell volume. Errors like tab-separated values were corrected in both categorical and target variables, ensuring data consistency. Class imbalance in the dataset was addressed using minority sampling techniques. Categorical features such as red blood cells, pus cells, bacterial presence, hypertension, diabetes, coronary artery disease, anemia, and pedal edema were strongly associated with CKD. Box plot analysis revealed outliers in features like age, blood glucose random, and specific gravity, but their removal was avoided due to the dataset's small size. Correlation analysis identified significant relationships, including a high positive correlation between hemoglobin, red blood cell count, and packed cell volume, leading to the retention of hemoglobin due to its clinical importance. Visualizations such as histograms, heatmaps, and box plots provided insights into data distribution, class imbalance, and feature importance for further analysis.


DATA PREPROCESSING


To prepare the CKD dataset for modeling, several preprocessing steps were applied. Numerical features were normalized using Standard Scaler to address skewness, ensuring a mean of zero and a standard deviation of one. Missing values were imputed using the mean for numerical data and the mode for categorical data, maintaining dataset integrity. Binary categorical variables were label-encoded (e.g., `ckd=1` and `notckd=0`), facilitating compatibility with machine learning algorithms. Class imbalance was resolved using the Synthetic Minority Over-sampling Technique (SMOTE), enhancing model reliability. Features `pcv` and `rbcc` were dropped, retaining `hemo` based on its importance in feature analysis and clinical relevance. Finally, the dataset was split into training and testing sets in an 80:20 ratio, ensuring readiness for model evaluation and generalization testing.

METHODOLOGY


In this project, three machine learning models were implemented for CKD classification: **Random Forest (RF)**, **Support Vector Machine (SVM)**, and **XGBoost**. These models were chosen for their proven performance and efficiency in structured data analysis.

1. **Random Forest**: Combines multiple decision trees using bagging and random feature selection to improve classification and reduce overfitting. Key hyperparameters, such as `n_estimators`, `max_depth`, and `min_samples_split`, were tuned. After addressing class imbalance with SMOTE and removing highly correlated features, RF achieved an accuracy of 96.25%.

2. **Support Vector Machine**: Utilized the RBF kernel to handle non-linear feature interactions. Key parameters like `gamma`, `C`, and `max_iter` were optimized for performance. Removal of highly correlated features and parameter tuning led to an accuracy of 93.75%.

3. **XGBoost**: A gradient-boosted tree algorithm designed for structured data problems. Hyperparameters, including `max_depth`, `learning_rate`, `n_estimators`, and `subsample`, were optimized for better performance. Feature selection and parameter adjustments improved the accuracy to 98.75%.

Each model's performance was evaluated using metrics such as accuracy, precision, recall, and F1-score, supported by confusion matrices and classification reports.

MODEL PERFORMANCE

Random Forest:

Accuracy: 96.25%
Class 0 (Non-CKD): Precision: 96%, Recall: 93%, F1-Score: 95%
Class 1 (CKD): Precision: 96%, Recall: 98%, F1-Score: 97%
Support Vector Machine (SVM):

Accuracy: 93.75%
Class 0 (Non-CKD): Precision: 100%, Recall: 82%, F1-Score: 90%
Class 1 (CKD): Precision: 91%, Recall: 100%, F1-Score: 95%
XGBoost:

Accuracy: 98.75%
Class 0 (Non-CKD): Precision: 97%, Recall: 100%, F1-Score: 98%
Class 1 (CKD): Precision: 100%, Recall: 98%, F1-Score: 99%
Feature Importance:
Consistent across all models, key features include:

Hemoglobin (Hemo): Critical for oxygen transport and indicative of CKD.
Specific Gravity (SG): Reflects urine concentration and kidney functionality.
Serum Creatinine (SC): A marker of kidney filtration efficiency.
Albumin (Al): Low levels suggest kidney damage.
Best Performing Model:

XGBoost delivered the highest accuracy, precision, and recall, making it the most reliable for CKD classification.

Limitations:
Small dataset size limits generalizability and use of advanced preprocessing methods like PCA.
Lack of demographic features like gender reduces diversity in predictions.
Synthetic data (SMOTE) may not fully capture real-world complexities, impacting reliability in practical scenarios.



