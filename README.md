# 🌌 Cosmic Classifier: Machine Learning Approach for Celestial Object Classification

---

## 📖 Overview

This project presents a comprehensive machine learning pipeline for the classification of celestial objects based on their physical and environmental characteristics, including atmospheric density, gravity, surface temperature, radiation levels, and other astrophysical parameters.

---

## 🗂️ Dataset

The dataset contained missing values, outliers, and moderate class imbalance, requiring extensive preprocessing to ensure robust model performance.

### Numerical Features
- Atmospheric Density
- Surface Temperature
- Gravity
- Water Content
- Mineral Abundance
- Orbital Period
- Proximity to Star
- Atmospheric Composition Index
- Additional physical attributes

### Categorical Features
- Magnetic Field Strength
- Radiation Levels

These categorical variables were transformed into numerical representations through category parsing and encoding.

---

## 🔍 Exploratory Data Analysis and Preprocessing

A detailed preprocessing pipeline was developed to improve data quality and model reliability.

### Class Distribution Analysis
- Examined class frequencies using `.value_counts()`.
- Least represented class (5.0): **5,132 samples**
- Most frequent class (1.0): **6,393 samples**

### Missing Value Treatment
- Approximately **5% missing values** were observed in each feature.
- Removed rows containing missing values in the target variable (**Prediction**).
- Applied **K-Nearest Neighbors (KNN) Imputation** to estimate missing feature values.

### Outlier Detection and Handling
- Outliers were identified using boxplot analysis, particularly in:
  - Gravity
  - Surface Temperature
- Applied **Winsorization** to limit the effect of extreme values while preserving observations.

### Correlation Analysis
- Investigated feature correlations to detect multicollinearity.
- No significant correlations were observed.

### Class Imbalance Handling
The following approaches were evaluated:

- Random Oversampling
- Random Undersampling
- SMOTE (Synthetic Minority Oversampling Technique)

**SMOTE** yielded the best results and was selected for the final pipeline.

---

## ⚙️ Model Development

### Models Used

- Random Forest Classifier
- XGBoost Classifier

The final model was constructed using a **VotingClassifier-based ensemble**, combining both algorithms to improve predictive robustness.

---

## 🎯 Hyperparameter Optimization

Hyperparameters were optimized using **GridSearchCV** with cross-validation.

### Why GridSearchCV?

- Performs exhaustive search over parameter combinations.
- Incorporates cross-validation to improve generalization.
- Supports parallel execution.
- Selected over RandomizedSearchCV to guarantee optimal parameter selection.

---

## 📊 Model Performance

| Metric | Score |
|----------|-------:|
| Accuracy | **0.9135** |
| F1 Score | **0.9134** |

---

## 🚀 Prediction on External Test Data

The notebook includes inference code for generating predictions on unseen datasets using the trained ensemble model.

---

## 🎓 Key Outcomes

- Demonstrated the effectiveness of ensemble learning for astrophysical object classification.
- Successfully addressed missing values, outliers, and class imbalance.
- Developed a robust preprocessing and feature engineering pipeline.
- Identified important features contributing to classification performance.
- Established a foundation for future extensions involving deep learning methods.

---

## 🏆 Achievement

Awarded **Third Prize** in the **Cosmic Classifier** competition organized by **IIT Roorkee** during **Cognizance 2025**, recognizing the project's technical rigor and classification performance.

---