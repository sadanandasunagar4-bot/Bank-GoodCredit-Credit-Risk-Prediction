# Bank GoodCredit – Credit Risk Prediction

## About the Project

Bank GoodCredit is a credit-risk prediction project focused on identifying customers who may have difficulty meeting their credit obligations.

I worked with banking data containing customer account information, enquiries, demographics, and payment-history information. The main challenge was not just building a machine learning model, but preparing messy real-world data properly before using it for prediction.

The project was developed using Python and MySQL as part of my Certified Data Scientist internship.

---

## What I Worked On

The project involved several stages, starting from data extraction and cleaning and ending with machine learning model evaluation.

### 1. Data Collection

The data was obtained from MySQL and included three main tables:

- Customer Account
- Customer Enquiry
- Customer Demographics

These tables had different row granularities, so the data had to be understood and combined carefully before modeling.

### 2. Data Cleaning

Before training the models, I worked on several data-quality issues.

Some of the main cleaning tasks included:

- Removing 2,401 duplicate account records
- Handling inconsistent data formats
- Fixing a date-parsing issue related to two-digit years
- Checking and removing duplicate or redundant engineered columns

### 3. Payment History Feature Engineering

Payment-history information was stored using status codes and delinquency values.

I converted these values into numerical features that could be used by machine learning models.

Some of the features created included:

- Average DPD
- Maximum DPD
- Number of reported payment months

These features helped represent a customer's repayment behaviour in a more useful form for credit-risk modeling.

### 4. Exploratory Data Analysis

I performed exploratory analysis to understand:

- Customer and account characteristics
- Payment behaviour
- Distribution of the target variable
- Missing and inconsistent values
- Relationships between important variables

This step helped identify data issues and understand the dataset before model training.

---

## Handling Class Imbalance

One of the important challenges in the project was the imbalance between good and bad customers.

The dataset contained approximately:

- **95.8% Good customers**
- **4.2% Bad customers**

Because of this imbalance, I compared two approaches:

- SMOTE oversampling
- Class weighting

The approaches were evaluated across multiple machine learning models to understand which method worked better for the problem.

---

## Machine Learning Models

I experimented with several classification algorithms:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Naive Bayes
- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost

For model comparison, I looked beyond accuracy and used metrics that are more useful for credit-risk classification.

---

## Model Evaluation

The models were evaluated using:

- Precision
- Recall
- F1-Score
- ROC-AUC
- Gini Coefficient

I also used cross-validation and hyperparameter tuning to improve model performance.

For selected models, GridSearchCV was used with ROC-AUC as the scoring metric.

---

## Final Result

After comparing the models and tuning the selected algorithms, **XGBoost achieved a test Gini of 39.35**.

The model was further evaluated using rank-ordering/decile analysis to understand how effectively it could separate customers according to risk.

---

## Tools and Technologies

**Programming:**  
Python, SQL

**Libraries:**  
Pandas, NumPy, Scikit-learn, XGBoost, Matplotlib, Seaborn

**Database:**  
MySQL

**Environment:**  
Jupyter Notebook

---

## Project Workflow

```text
MySQL Data
    ↓
Data Extraction
    ↓
Data Cleaning
    ↓
Exploratory Data Analysis
    ↓
Payment History Feature Engineering
    ↓
Data Preprocessing
    ↓
Class Imbalance Handling
    ↓
Model Training
    ↓
Model Comparison
    ↓
Hyperparameter Tuning
    ↓
Model Evaluation
    ↓
Decile / Rank-Ordering Analysis
