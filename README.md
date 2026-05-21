# Loan Default Prediction Project

## Project Overview

This project focuses on predicting loan default risk using supervised machine learning techniques. The objective is to classify whether a borrower will default on a loan based on demographic, financial, employment, and loan-related information.

The project follows a complete machine learning workflow including:
- data preprocessing
- feature engineering
- model training
- hyperparameter optimisation
- model evaluation
- Kaggle submission generation

Multiple classification algorithms were implemented and compared to identify the best-performing model.

---

# Dataset Information

The project uses the following datasets:

| Dataset | Description |
|---|---|
| `Assignment3-Loan-Dataset.csv` | Labelled dataset used for training and evaluation |
| `Assignment3-Unknown-Dataset.csv` | Unlabelled dataset used for final Kaggle prediction |
| `Assignment3-Kaggle-Submission-Sample.csv` | Sample submission format |

## Target Variable

`loan_default`
- `0` → No Default
- `1` → Default

---

# Project Objectives

The objectives of this project are to:

- Build multiple classification models
- Compare model performance
- Apply preprocessing and feature engineering
- Optimise hyperparameters
- Select the best-performing classifier
- Generate predictions for unseen data
- Produce a valid Kaggle submission

---

# Machine Learning Models Used

The following classifiers were implemented:

1. Decision Tree
2. K-Nearest Neighbours (KNN)
3. Random Forest
4. Nu Support Vector Machine (NuSVC)
5. Multi-Layer Perceptron Neural Network (MLP)

---

# Data Preprocessing

## Missing Value Handling

- Numerical missing values were imputed using the median
- Categorical missing values were replaced with `"Unknown"`

## Encoding

- One-Hot Encoding was applied to nominal categorical variables
- Ordinal Encoding was applied to ordered categories

## Feature Scaling

`StandardScaler` was applied to:
- KNN
- NuSVC
- Neural Network

## Feature Engineering

Additional features created:
- `loan_to_income`
- `expense_to_income`
- `balance_to_loan`

These features help capture borrower financial stress more effectively.

---

# Dataset Partitioning

The dataset was split using stratified sampling:

- 60% Training Set
- 20% Validation Set
- 20% Test Set

The validation set was used for hyperparameter tuning, while the test set was reserved for final evaluation.

---

# Hyperparameter Optimisation

Each model was tuned using the validation set.

Examples include:
- Decision Tree → `max_depth`
- KNN → `k`
- Random Forest → `n_estimators`, `max_depth`
- NuSVC → `nu`
- Neural Network → hidden layer sizes

---

# Evaluation Metrics

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Sensitivity
- Specificity
- ROC-AUC

Special attention was given to recall and AUC due to the importance of identifying default borrowers.

---

# Best Model

The best-performing model was **Random Forest**.

Reasons:
- highest validation performance
- strong ROC-AUC score
- robust generalisation
- effective handling of feature interactions
- best Kaggle performance

---

# Kaggle Submission

The final Random Forest model was used to generate predictions for the unknown dataset.

The submission file contains:
- `row ID`
- `Predicted-Loan-Default`

---

# Technologies Used

- Python
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

---

# Installation

Install required libraries:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
