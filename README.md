# Assesment-Loan-Repayment-
Building a Predictive Model to Assess Loan Repayment Risk and Boost Profitability


# 🛒 **Building a Predictive Model to Assess Loan Repayment Risk and Boost Profitability** 🛒
---
## 📂 **Stage 0 : Problem Statement**
### Problem Statement
- 8.1% of clients experience difficulties in loan repayment, while 91.9% have no issues. This presents an opportunity for the company to increase the number of clients who make timely payments while reducing repayment difficulties. This ensures safer loan distribution and has the potential to enhance profitability.
  <p align="center">
<img src="!https://github.com/user-attachments/assets/4d96feab-b5ac-42e4-a8c4-2ee9eb8c5f34"
 alt="MultivariateAnalysis">
</p>

- A predictive strategy is needed to identify high-risk clients so that loans can be directed appropriately or rejected if they pose a risk of non-payment.

### Goal
- Develop a machine learning model to predict the risk of loan repayment difficulties.

### Objectives
- Develop a predictive model to project the risk of loan repayment difficulties.
- Identify patterns and key factors influencing repayment ability to support strategic decision-making.
  
### Business Matrics
-  ROC-AUC for evaluating model performance.
<br>

---
<br>

## 📂 **Stage 1 : Exploratory Data Analysis**
### Dataset
- Dataset Loan 2007-2014
- Rows : 466285
- Columns : 75
- Columns-Null : 40 Columns
- Duplicates Data : 0
</p>
<br>

## 📂 **Stage 2 : Feature Engineering**
<p align="center">
<img src="https://github.com/user-attachments/assets/886250d9-6221-458f-90e0-e0fa18128d66"
 alt="Proportionloan">
</p>
<br>

### Data Preprocessing Summary:

1. Feature Removal:
- Drop columns with >70% missing values.
- Exclude identifiers (e.g., id, id anggota, url, etc.).
- Remove sub_grade (duplicates information from grade).
- Exclude future-related features (e.g., next_pymnt_d, recovery, etc.).

2. Loan Status Classification:
- Bad Loans (1): Charged Off, Default, Late (31-120 days), Late (16-30 days), Does not meet the credit policy. Status: Charged Off.
- Good Loans (0): Fully Paid, Current, In Grace Period, Does not meet the credit policy. Status: Fully Paid.

3. Target Variable Creation:
- Create a binary variable: good (0) and bad (1) loans.
<br>

## 📂 **Stage 3 : Exploratory Data Analysis**
<p align="center">
<img src="https://github.com/user-attachments/assets/6fcab117-4c78-4587-bccd-ab6a5f1dabca"
 alt="MultivariateAnalysis">
</p>

The heatmap highlights significant correlations among payment variables, such as total_rec_int with total_pymnt (0.60) and last_pymnt_amnt with total_pymnt (0.64). Weak correlations exist between loan_bad and variables like annual_inc (0.04, positive), dti (-0.06), and int_rate (-0.17, both negative), suggesting minimal influence on default risk. Most other features show low, likely insignificant correlations.

Data distribution is imbalanced, with most features highly skewed and concentrated in specific ranges, alongside notable outliers. The target variable, loan_bad, also shows class imbalance, requiring adjustments for effective classification modeling.
<br>

## 📂 **Stage 4 : Data Preparation**
<br>
1. Data Preparation
- Data transformation
- Handling missing value
- Feature encoding : OHE
- Feature selection : Teknik WoE dan IV
- Feature Extraction

2. New Features Based WoE and IV
- Spliting Data : Train & Test
- Class Imbalance : RandomOverSampler
- Modelling

<p align="center">
<img src="https://github.com/user-attachments/assets/d528b2c7-b2ed-4699-9968-56384d4ba2ae"
 alt="JumlahData">

## 📂 **Stage 5 : Data Modeling**

<p align="center">
<img src="https://github.com/user-attachments/assets/26c4db70-addd-41d5-9fe5-2fbc55f347f4"
 alt="DataModeling">
</p>

<br>
 <p align="center">
<img src="https://github.com/user-attachments/assets/6f647df2-fd8e-44d4-800b-aa9b417d7bfe"
 alt="DataModeling">
 </p>
 
The Logistic Regression model shows a robust performance with an ROC AUC of 0.858 on both the cross-validation training and test sets. This suggests that the model performs consistently well in distinguishing between classes across different thresholds of probability, despite some imbalance in the data. The ROC AUC score indicates a good trade-off between True Positive Rate (TPR) and False Positive Rate (FPR).

## 📂 **Stage 6 : Model Evaluation**

<br>
 <p align="center">
<img src="https://github.com/user-attachments/assets/a6002c17-e51f-436f-89a8-85781c252391"
 alt="ModelEvaluation">
 </p>

- Gini = (roc_auc * 2) - 1
- Gini : 0.701925

Reliable Predictive Performance
With an ROC-AUC of 0.850963, the model demonstrates exceptional performance in distinguishing between Bad Loan and Good Loan. It proves to be highly reliable in predicting default risk.

Strong Gini Coefficient
A Gini value of 0.701925 indicates the model's effectiveness in separating positive and negative classes. This serves as a strong indicator of the model's predictive power, even in the presence of imbalanced data.

## 📂 **Stage 7 : Recommendation and Conclusion**

A. Based on the best Logistic Regression model, here are the recommendations for managing loan credit:
1. Total Payment (total_pymnt): Focus on high-paying customers. Offer incentives like discounts or special promos for those paying over 22,000.
2. Total Interest Received (total_rec_int): Tailor approaches for customers with high interest income. Offer premium product access to those with more than 9,000.
3. Outstanding Loan Balance (out_prncp): Review policies for customers with small balances. For balances under 3,000, offer more flexible repayment options.
4. Interest Rate (int_rate): Provide attractive offers for customers with low-interest rates, such as further financing or refinancing options.

B. Model Analysis: 
- The Logistic Regression model shows a portfolio consisting of 61.13% good loans and 38.87% risky loans. 15.01% of good loans are invested. For every 100 loans avoided, 97.95% are risky (98 risky and 2 good loans).


