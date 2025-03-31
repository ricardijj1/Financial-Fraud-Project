📘 README: Fraud Detection with Multiple ML Models

# Project Title:
Financial Fraud Dataset - Basic Pipeline 


# 📂 Dataset Description
The dataset used in this project contains anonymized financial transaction records. Each row represents a single transaction, and the goal is to classify whether the transaction is fraudulent (1) or legitimate (0). Fraudulent transactions are rare, which introduces a significant class imbalance—a central challenge in this project.

# Columns Overview

● Step: A unit of time that represents hours in the dataset. Think of this as the timestamp of the transaction (e.g. hour 1, hour 2, … hour 534, …) 
● Type: The type of transaction 
● Amount: The amount of money transferred 
● NameOrig: The origin account name
● OldBalanceOrg: The origin accounts balance before the transaction ● NewBalanceOrg: The origin accounts balance after the transaction 
● NameDest: The destination account name 
● OldbalanceDest: The destination accounts balance before the transaction ● NewbalanceDest: The destination accounts balance after the transaction 
● IsFlaggedFraud: A “naive” model that simply flags a transaction as fraudulent if it is greater than 200,000 (note that this currency is not USD) 
● IsFraud: Was this simulated transaction actually fraudulent? In this case, we consider “fraud” to be a malicious transaction that aimed to transfer funds out of a victim’s bank account before the account owner could secure their information.

# Project Goals
- Perform EDA
- Data cleaning and wrangling
- Model trainning and evaluation. 

## Exploratory Data Analysis (EDA)
For my EDA, I went through univariate, bivariate, and multivariate analysis. This helped me get a better understanding of the dataset and the different distributions across features. I started to notice patterns and trends, like how the fraudulent transactions were very few and clearly underrepresented. One common pattern was that fraud often involved draining accounts completely. I also decided that the destination columns weren’t useful for my analysis or modeling, so I dropped them.

## Data Cleaning
To prepare the data for analysis, I dropped irrelevant columns like NameOrig and NameDest, since they didn’t offer any value for modeling. I also created a new feature called balance_difference, which is the difference between old balance (origin) and new balance (origin). This helped me explore whether that difference matched the amount column, and whether mismatches could be a sign of fraud. 

## Model Training & Evaluation
My logistic regression model had really high accuracy around 99.9%  which li thought was great at first. But since fraud is so rare, even a model that predicts “not fraud” for everything would still score high on accuracy. What i think matters here is recall and precision. The precision was solid, when the model predicted fraud, it was usually right. But the recall was only about 44%, so a lot is missed.Going forward, I want to adjust the model using smote.


# Tools & Libraries
- Python
- Pandas & NumPy
- Matplotlib & Seaborn
- scikit-learn


