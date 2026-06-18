# Diabetes Prediction Using Support Vector Machine (SVM)

# Project Overview

This project predicts whether a patient is diabetic or non-diabetic using the Pima Indians Diabetes Dataset. 
The model was developed using: 
Python, Pandas, NumPy, and Scikit-learn

The main goal of this project was to practice and reinforce fundamental machine learning concepts, including data preprocessing, feature standardization, train-test splitting, model training, evaluation, and prediction.

# Dataset

The project uses the Pima Indians Diabetes Dataset, which contains medical information about patients, including:

Pregnancies
Glucose
Blood Pressure
Skin Thickness
Insulin
BMI
Diabetes Pedigree Function
Age

=>  https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database 

# Target variable:

0 = Non-diabetic
1 = Diabetic

# Technologies Used

Python
NumPy
Pandas
Scikit-learn
Google Colab

# Machine Learning Workflow

Load and explore the dataset.
Analyze data distributions and class counts.
Separate features and labels.
Standardize the feature values using StandardScaler.
Split the dataset into training and testing sets.
Train a Support Vector Machine (SVM) classifier.
Evaluate model performance using accuracy score.
Build a simple predictive system for new patient data.

# Results
Training Accuracy: Approximately 78.7%
Testing Accuracy: Approximately 77.3%

The training and testing accuracies are relatively close, indicating that the model generalizes reasonably well on unseen data.

# What I Learned

Through this project, I practiced:

Data preprocessing and cleaning
Feature scaling using StandardScaler
Train-test splitting
Working with Scikit-learn
Training an SVM classifier
Evaluating classification models
Making predictions on new data

# Future Improvements

Perform hyperparameter tuning
Compare SVM with Logistic Regression and Random Forest
Use cross-validation
Handle missing or zero values more carefully
Build a web application using Streamlit or Flask

# Educational Purpose

This project was completed as part of my machine learning learning journey to strengthen my understanding of supervised learning and classification algorithms.
