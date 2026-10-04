# AI/ML Inovegen Internship

This repository contains my work for the four-week AI/ML internship at Inovegen.

## Week 1: Data Cleaning and Exploratory Data Analysis

- Cleaned and analyzed the Titanic dataset
- Handled missing values and duplicate records
- Performed exploratory data analysis and visualizations

Files:
- `data_cleaning(week1).ipynb`
- `Titanic-Dataset.csv`

## Week 2: Classification Model and Evaluation

- Used the Breast Cancer Wisconsin Diagnostic dataset
- Checked missing values, duplicates, and data quality
- Compared Logistic Regression and Random Forest with a baseline model
- Evaluated models using accuracy, precision, recall, F1-score, and ROC-AUC
- Included confusion matrices, ROC curves, cross-validation, and feature importance

File:
- `Inovegen_Week2_Breast_Cancer_Classification.ipynb`

## Week 2 Key Result

Logistic Regression achieved approximately 95.6% test accuracy and 0.995 ROC-AUC.

## Task 3 - Customer Churn Prediction

### Objective

Predict whether a telecommunications customer will churn using the IBM Telco Customer Churn dataset.

### Preprocessing

- Converted `TotalCharges` from text to numeric.
- Identified and removed 11 rows with blank `TotalCharges`.
- Checked exact duplicates and duplicate customer IDs.
- Removed `customerID` from modelling because it is a unique identifier.
- Encoded `Churn` as 1 for Yes and 0 for No.
- Standardized numeric variables and one-hot encoded categorical variables inside a leakage-safe pipeline.
- Used an 80/20 stratified train/test split.

### Exploratory analysis

The notebook includes churn distribution, churn rate by contract type, monthly charges by churn status, and churn rate by tenure group.

### Models and evaluation

- Dummy majority-class baseline
- Logistic Regression with balanced class weights
- Random Forest with balanced class weights

Models are evaluated using accuracy, precision, recall, F1-score, ROC-AUC, confusion matrices, ROC curves and five-fold cross-validation.

Verified test-set results:

| Model | Accuracy | Precision | Churn recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Dummy baseline | 73.4% | 0.0% | 0.0% | 0.0% | 50.0% |
| Logistic Regression | 72.6% | 49.0% | 79.7% | 60.7% | 83.5% |
| Random Forest | 77.5% | 57.0% | 62.8% | 59.8% | 82.5% |

Logistic Regression was selected as the preferred retention-screening model because it detected the highest proportion of actual churners and achieved the strongest F1-score and ROC-AUC. Random Forest produced higher overall accuracy and precision but missed more churners.

### Main findings

- Month-to-month contracts are associated with substantially higher churn.
- Churn is highest among customers with short tenure.
- Customers who churn tend to have higher monthly charges.
- Trained models identify churners more effectively than the majority-class baseline.
- Model selection should consider churn recall and business cost, not accuracy alone.

### Task 3 files

- `Inovegen_Task3_Customer_Churn_Prediction.ipynb`
- `Telco_Customer_Churn.csv`

### Dataset source

IBM Telco Customer Churn repository:  
https://github.com/IBM/telco-customer-churn-on-icp4d

## Running the Task 3 notebook

Open the notebook in Google Colab or Jupyter and select **Run all**. Keep the CSV in the same working folder. If the local CSV is unavailable, the notebook attempts to load the same public dataset from IBM's repository.

