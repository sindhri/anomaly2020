# Anomaly detection using account and transaction information
* anomaly2020 for Hackmaker #digitaldefense

## Why anomaly detection? 
* It helps organizations fight against fraud and protect cyber security.
* Anomaly detection has many challenges, such as there tend to be a high rate of false positives when modeling normal activities.
* Anomaly detection can also be very costly if human has to manually evaluate each transaction.
* Thus an autonomous and systematic approach to anomaly detection is highly desired.

## Problem statement:
* We are looking for fraudulent activities in 1.5 million transactions. We are given account information and transaction information.
* For each account the following information is provided:
* ACCTTYPE, ACCTNAME, FIRSTNAME, SURNAME, DOB, ACCTCREATED, ACCTRISK, ADDRESS, ADDRESS_LAT, ADDRESS_LON, CATEGORY
* For each transaction the following information is provided:
* TXN_ID, TXTYPE, AMOUNT, FROMACCTID, TOACCTID, TXDATE, REFERENCE, ISFRAUD, ISFLAGGED

## Solution: 
* We took a 7-step approach to compose an autonomous systematic anomaly detection. 
* We evaluated transactions based on 
* 1.duplicated account 
* 2.account risk level 
* 3.account category
* 4.rare events
* 5.abnormal days
* 6.frequently references transactions
* 7.abnormal individual accounts

## 1. duplicated accounts
* Accounts with the same name and type
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/duplicate_account_example.png" width = "900">

## 2. Account Risk Level
* Amount > 100000 and either the from account or to account is medium or high risk
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/risk_amount.png" width = "900">

## 3. Account category
* Outliers compare to transactions from the same category
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/boxplot_FROMACCT_CATEGORY_outlier.png" width = "900">
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/boxplot_TOACCT_CATEGORY_outlier.png" width = "900">

## 4. Rare events
* Rare events are focused in a few categories: Brewery, Clinic, Consulting, Tranding, Finance. They have infrequent transactions but with very large and simmilar amounts.
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/boxplot_FROMACCT_CATEGORY_rare.png" width = "900">
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/boxplot_TOACCT_CATEGORY_rare.png" width = "900">

## 5. Abnormal days
* On Feburary 28, 2020, the average amount in each transaction was 10 times as in other days
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/day_mean_transaction_list.png" width = "400">
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/day_mean_transaction.png" width = "900">

## 6. Most frequent references
* Several references were used 10 times more than the rest of the references: 
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/counts_reference_list.png" width = "400">
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/counts_reference.png" width = "900">

## 7. Individual abnormal accounts
* Transactions among them were infrequent but with large amounts
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/individual_account1.png" width = "400">
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/individual_account2.png" width = "400">
<img src = "https://github.com/sindhri/anomaly2020/blob/main/img/individual_account3.png" width = "400">

# Conclusion:
* Our 7-step solution is able to detect anomaly in an autonomous and systematic way

# Next step:
* Predictive Modeling



