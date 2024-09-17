# Cybersecurity Incident Triage Prediction

## Project Overview
This project aims to improve the efficiency of Security Operation Centers (SOCs) by developing a machine learning model that predicts the triage grade of cybersecurity incidents—True Positive (TP), Benign Positive (BP), or False Positive (FP)—based on historical data from the GUIDE dataset. The model aids in automating the triage process, allowing SOC analysts to focus on critical incidents.

## Business Use Cases
- **SOCs**: Automate triage, enabling SOC analysts to respond to threats more efficiently.
- **Incident Response**: Suggest guided responses for quicker mitigation.
- **Threat Intelligence**: Enhance detection by incorporating customer responses into predictions.
- **Enterprise Security**: Reduce false positives and address real threats promptly.

## Approach

### 1. Data Preprocessing
- **Missing Data**: Identified missing columns and removed them from the dataset.
- **Datetime Handling**: Converted the timestamp column into datetime format and split it into separate date and time columns.
- **Resampling**: Resampled the data to ensure balanced class distribution.

### 2. Feature Engineering
- **Chi-Square Test**: Used chi-square to assess feature relevance for categorical variables.
- **Multiple Correspondence Analysis (MCA)**: Applied MCA to extract relationships between categorical variables.
- **Random Forest**: Built a feature importance ranking based on the Random Forest model.

### 3. Model Training
We trained and compared multiple machine learning models:
- **Logistic Regression (LR)**
- **Random Forest (RF)**
- **XGBoost (XGB)**

We performed hyperparameter tuning using grid search and tracked the results with **MLflow**.

### 4. Model Evaluation
We compared models based on precision, recall, F1-score, and accuracy. The Random Forest and XGBoost models yielded the best results.

### 5. Final Results

- **Internal Test Results**:
  - **Class 0**: Precision = 0.91, Recall = 0.92, F1-Score = 0.92
  - **Class 1**: Precision = 0.91, Recall = 0.94, F1-Score = 0.92
  - **Class 2**: Precision = 0.95, Recall = 0.91, F1-Score = 0.93
  - **Overall Accuracy**: 0.92
  - **Macro Avg**: Precision = 0.92, Recall = 0.92, F1-Score = 0.92
  - **Weighted Avg**: Precision = 0.92, Recall = 0.92, F1-Score = 0.92

- **External Test Results**:
  - **Class 0**: Precision = 0.91, Recall = 0.87, F1-Score = 0.89
  - **Class 1**: Precision = 0.79, Recall = 0.88, F1-Score = 0.84
  - **Class 2**: Precision = 0.92, Recall = 0.90, F1-Score = 0.91
  - **Overall Accuracy**: 0.89
  - **Macro Avg**: Precision = 0.87, Recall = 0.89, F1-Score = 0.88
  - **Weighted Avg**: Precision = 0.89, Recall = 0.89, F1-Score = 0.89

### 6. Model Deployment
The model is prepared for deployment, where it can be integrated into SOC workflows for automated triage and guided response.

## Technology Stack
- **Python**: For data manipulation and modeling.
- **Pandas, NumPy**: Data preprocessing and feature engineering.
- **Scikit-learn, XGBoost**: Model training and evaluation.
- **MLflow**: Tracking experiments and models.
- **Matplotlib, Seaborn**: Visualization.
