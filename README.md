# Loan Approval Prediction – Data Analysis Project

## Student Information
- **Name:** Abdallah Salah  
- **Group Code:** AST4_AIS2_S1  
- **Instructor:** Eng. Mahmoud Talaat  
- **Program:** DEPI – Round 4  
- **Track:** AI & Data Science - Microsoft Machine Learning Engineer 

---

## Project Overview
This project focuses on performing a complete data analysis pipeline on a loan approval dataset.  
The objective is to explore, clean, prepare, and analyze the data in order to identify the most impactful features influencing the loan approval decision (`Loan_Status`).

---

## 1. Data Reading
- The dataset is loaded using **Pandas**.
- Data types, structure, and basic statistics are inspected.
- Initial checks are performed using:
  - `head()`
  - `info()`
  - `describe()`

---

## 2. Exploratory Data Analysis (EDA)

### 2.1 Categorical Features
Categorical features were analyzed using:
- **Bar charts**
- **Pie charts**

These visualizations were used for:
- Gender
- Married
- Education
- Self_Employed
- Property_Area
- Loan_Status

This analysis helped identify class imbalance and dominant categories.

---

### 2.2 Continuous Features
Continuous variables were explored using:
- **Scatter plots**
- **Histograms**

Features analyzed include:
- ApplicantIncome
- CoapplicantIncome
- LoanAmount
- Loan_Amount_Term

These plots helped understand:
- Data distribution
- Relationships between numerical variables
- Skewness in income and loan amount

---

### 2.3 Outlier Detection
Outliers were identified using:
- **Box plots**

Box plots were used to:
- Detect extreme values
- Compare distributions across categories
- Support decisions for outlier treatment

---

## 3. Data Cleaning

### 3.1 Duplicate Values
- The dataset was checked for duplicates.
- Duplicate records were removed when found.

### 3.2 Missing Values
Missing values were handled as follows:
- Numerical features: filled using **median**
- Categorical features: filled using **mode**
- In some cases, rows were dropped when missing data was insignificant

---

### 3.3 Outlier Treatment
Outliers were treated using:
- **Interquartile Range (IQR) method**

Extreme values outside acceptable bounds were either:
- Capped
- Removed if they significantly distorted the data

---

## 4. Data Preparation

### 4.1 Encoding Categorical Variables
Categorical variables were encoded using:
- **Manual label encoding** for binary features
- **One-hot encoding** for multi-class features

This ensured full control over encoded values.

---

### 4.2 Numeric Transformation
- All features were transformed into numeric format.
- The dataset became fully compatible with correlation analysis and machine learning models.

---

## 5. Feature Analysis

### 5.1 Correlation Analysis
- **Pearson correlation** was calculated between each feature and the target variable.
- A **correlation heatmap** was used for visualization.

---

### 5.2 R-Squared Calculation
- R² values were calculated as the square of Pearson correlation.
- This helped measure how much variance in `Loan_Status` is explained by each feature.

---

### 5.3 Feature Importance Evaluation
- Features were ranked based on:
  - Correlation strength
  - R² values
  - Domain relevance

---

## 6. Insights & Feature Selection

### Key Insights
- **Credit_History** is the most influential feature with a strong positive correlation.
- Income-related features affect loan approval indirectly through loan amount.
- Most categorical variables show weak linear relationships individually.
- Loan approval decisions are likely influenced by non-linear interactions.

---

### Selected Features
Based on statistical analysis and domain understanding, the following features were selected:

```text
Credit_History
ApplicantIncome
CoapplicantIncome
LoanAmount
Education
Married
```

### Features Removed
The following features showed minimal impact and were removed to simplify the model:
- Gender
- Dependents
- Self_Employed
- Loan_Amount_Term

### Conclusion
Correlation analysis is effective for initial feature screening.
Credit history plays a critical role in loan approval.
Feature engineering and multivariate models are recommended for better performance.
The final dataset is clean, numeric, and ready for modeling.

### Tools & Libraries Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
