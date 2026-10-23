# Diabetes Risk Factor Analysis & Machine Learning

### Exploratory Data Analysis | Healthcare Analytics | Machine Learning
<img width="1338" height="757" alt="image" src="https://github.com/user-attachments/assets/797e1ecf-0ad2-42c6-96fe-fa52de504df2" />

## Overview

This project explores the relationship between patient health measurements and diabetes outcomes using the Pima Indians Diabetes Dataset.

I initially explored diabetes prediction through a guided machine-learning tutorial. I later expanded the work into an independent analysis, focusing on data quality, exploratory data analysis, model comparison, and interpretation.

The goal was not only to predict diabetes outcomes, but also to understand how different medical measurements relate to the outcome and how preprocessing decisions affect a machine-learning workflow.

## Research Questions

1. Which patient characteristics are most strongly associated with diabetes outcomes?
2. What data-quality issues exist in the dataset, and how should they be handled?
3. How do Logistic Regression, Support Vector Machine, and Random Forest compare in classification performance?
4. Why is recall particularly important when evaluating a healthcare-related classification model?

## Dataset

The project uses the Pima Indians Diabetes Dataset, containing 768 observations and eight predictor features.

**Features:** Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, and Age.

**Target:** Outcome (0 = negative, 1 = positive).

The dataset represents women of Pima Indian heritage aged at least 21, so the results should not be generalized to all populations.

## Project Workflow

### 1. Exploratory Data Analysis

I investigated descriptive statistics, feature distributions, potential data-quality issues, and relationships between patient characteristics and diabetes outcomes.

Key findings included:

- Patients with positive outcomes generally had higher glucose, BMI, and age measurements.
- Glucose showed the strongest positive Pearson correlation with the outcome (r ≈ 0.47).
- Pregnancies and Age showed a positive correlation (r ≈ 0.54).
- Several medical features contained implausible zero values.

### 2. Data Quality and Preprocessing

Although the dataset contained no explicitly recorded null values, several measurements included suspicious zeros.

Approximately **48.7% of insulin measurements** were recorded as zero.

I treated zero values in Glucose, BloodPressure, SkinThickness, Insulin, and BMI as potentially missing measurements, while preserving valid zeros in Pregnancies and Outcome.

I implemented preprocessing using scikit-learn pipelines, including:

- Median imputation for suspicious zero measurements.
- StandardScaler for numerical features.
- Stratified 80/20 train/test splitting.
- Training-only fitting of preprocessing transformations to reduce data leakage.

### 3. Machine Learning

Three classification models were evaluated:

- Logistic Regression
- Support Vector Machine (linear kernel)
- Random Forest

I compared the models using five-fold stratified cross-validation on the training set, evaluating Accuracy, Recall, F1-score, and ROC-AUC.

## Model Results

### Five-Fold Cross-Validation (Training Data)

| Model | Accuracy | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.788 | 0.575 | **0.655** | 0.843 |
| Linear SVM | 0.788 | 0.570 | 0.652 | **0.845** |
| Random Forest | 0.764 | **0.584** | 0.632 | 0.817 |

Logistic Regression achieved the highest mean F1-score, while SVM achieved a marginally higher mean ROC-AUC.

### Test-Set Performance

| Model | Accuracy | Recall | F1-score |
|---|---:|---:|---:|
| Logistic Regression | 70.78% | 50.00% | 54.55% |
| Linear SVM | 70.13% | 48.15% | 53.06% |
| Random Forest | **72.73%** | **55.56%** | **58.82%** |

Random Forest achieved the highest scores on this particular test split, although cross-validation produced a different model ranking.

The test set was examined during model development, so these results should be interpreted as exploratory rather than a fully independent final assessment.

## Model Interpretation

I examined the standardized coefficients of Logistic Regression to understand the direction and relative magnitude of model associations.

Glucose and BMI had the largest positive coefficients, consistent with the exploratory analysis.

However, model coefficients indicate statistical relationships in the fitted model, not causal effects.

The Logistic Regression confusion matrix also revealed 27 false negatives among 54 actual positive cases. This highlights the importance of recall when considering healthcare-related classification applications.

## Limitations

- The dataset is relatively small and represents a specific population.
- Several features contain potentially missing or invalid measurements.
- The models were not externally validated.
- The test set was inspected during development.
- Model predictions and associations should not be interpreted as medical diagnoses or
