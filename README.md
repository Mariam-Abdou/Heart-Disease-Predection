# Heart Disease Prediction using Machine Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0%2B-orange)
![Pandas](https://img.shields.io/badge/Pandas-1.3%2B-lightgrey)  
*A predictive analytics project to assess heart disease risk using clinical features.*

## 📌 Project Overview
This project demonstrates a comprehensive approach to analyzing heart failure data, blending statistical analysis with machine learning to support early diagnosis and effective risk stratification.

- Predicts heart disease risk using patient clinical data.
- Compares 4 ML models and hierarchical clustering for patient stratification.
- Identifies key biomarkers (e.g., cholesterol, ST depression) influencing predictions.

## Key Objectives
- Perform **exploratory data analysis** to uncover meaningful patterns and trends.
- Build **machine learning models** for predicting heart failure risk, including:
  - Naïve Bayes
  - Support Vector Machines (SVM)
  - K-Nearest Neighbors (KNN)
  - Decision Trees
- Utilize **hierarchical clustering** to visualize relationships between patient groups with a dendrogram.

  
## 📂 Dataset
**Source**: [Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)  


## 🛠️ Workflow
   
### 1. Data Preprocessing
Cleaning and preprocessing the dataset to handle inconsistencies and ensure quality input for modeling.
- **Cleaning**: Fixed negative values, retained clinically valid outliers.
- **Encoding**: Label-encoded categorical features.
- **Scaling**: Standardized numerical features using `StandardScaler`.
- **PCA**: Reduced dimensions for clustering visualization.

### 2. Dimensionality Reduction
Applied PCA (preserved 85% variance) to reduce 11 features → 2 principal components


### 3. Model Training & Evaluation
Trained multiple classifiers and compared them to determine the most effective approach for risk prediction.

4 models trained using **GridSearchCV** (5-fold cross-validation):

| Model               | Best Parameters                          | Test Accuracy | Recall |
|---------------------|-----------------------------------------|---------------|--------|
| SVM                 | `C=10`, `kernel='rbf'`, `gamma=0.01`    | 89.1%         | 88.5%  |
| KNN                 | `n_neighbors=9`, `metric='manhattan'`   | 86.9%         | 85.2%  |
| Decision Tree       | `max_depth=4`, `criterion='gini'`       | 84.3%         | 82.1%  |
| Naïve Bayes         | `var_smoothing=1e-9`                    | 83.5%         | 80.7%  |


### 4. Hierarchical Clustering
Examined natural groupings within the patient data to provide additional insights.
- Applied 5 linkage methods (`single`, `complete`, `ward`, etc.) to identify patient subgroups.
- **Ward linkage** best aligned with disease classes (silhouette score: 0.62).  


## 📊 Results Summary
| Model       | Accuracy | Precision | Recall | F1-Score |
|-------------|----------|-----------|--------|----------|
| SVM         | 89.1%    | 88.3%     | 88.5%  | 88.4%    |
| KNN         | 86.9%    | 86.2%     | 85.2%  | 85.7%    |
| Decision Tree | 84.3%  | 83.1%     | 82.1%  | 82.6%    |

