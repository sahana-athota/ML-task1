# Student Romantic Relationship Prediction

## Project Overview
This project develops a machine learning model to predict whether a student is in a romantic relationship based on various demographic, academic, and behavioral features from a student dataset. The primary goal is to understand the factors that influence romantic relationship formation among students.

## Dataset
The dataset contains information about students including:
- **Demographic features**: age, sex, family size, parent education
- **Academic features**: school performance (G1, G2, G3), absences, school support
- **Social/Behavioral features**: going out frequency, free time, travel time, activities participation
- **Target variable**: `romantic` 

## Approach

### 1. Exploratory Data Analysis (EDA)
- Comprehensive statistical analysis of all features
- **Correlation matrix analysis** to identify relationships between features and target variable
- Distribution analysis to understand data patterns and class imbalance
- Feature importance visualization using correlation heatmaps

### 2. Data Preprocessing
- **Label Encoding**: Applied to ordinal categorical variables 
- **One-Hot Encoding**: Applied to nominal categorical variables 
- **Standard Scaler**: Normalized numerical features to ensure equal weight in model training
- **Missing Value Handling**: Addressed any missing values through appropriate imputation strategies

### 3. Model Selection Strategy
Given the **class imbalance** in the romantic relationship target variable, the evaluation focused on:
- **ROC-AUC Score** as primary metric (more robust for imbalanced datasets)
- **Precision-Recall curves** for additional validation

### 4. Classification Models Tested
Multiple classification algorithms were evaluated:
- **Random Forest Classifier** (final choice)
- Logistic Regression
- Support Vector Machine (SVM)
- Gradient Boosting Classifier
- K-Nearest Neighbors (KNN)

**Random Forest was selected** based on:
- Highest ROC-AUC score
- Built-in feature importance ranking

## Key Findings

### Feature Importance Analysis
The correlation matrix and Random Forest feature importance revealed key predictors:
- **Travel time**: Students with longer commutes showed lower relationship rates
- **Going out frequency**: Strong positive correlation with romantic relationships
- **Age**: 15-18 aged students are more likely to be in relationships

### Model Performance
- **ROC-AUC Score**: 58.7
- **Precision**: 58
- **Recall**: 60
- **F1-Score**: 59


## Technical Implementation

### Why ROC-AUC Over Accuracy?
The dataset showed class imbalance with fewer students in romantic relationships. **ROC-AUC** was chosen as the primary evaluation metric because:
- **Accuracy can be misleading** with imbalanced classes (high accuracy by predicting majority class)
- **ROC-AUC measures** the model's ability to distinguish between classes across all thresholds
- **Better representation** of model performance for minority class prediction


## Future Improvements
- **Feature engineering**: Create interaction terms between key variables
- **Advanced algorithms**: Experiment with ensemble methods and neural networks
- **External validation**: Test model on different student populations




