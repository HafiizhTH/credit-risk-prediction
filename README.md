# credit-risk-prediction
This repository contains a project from the Program Based Internship Data Scientist from the ID/X Partner company in collaboration with Rakamin Academy.

## Background
**Business Understanding:**  
ID/X Partners (PT IDX Consulting) was established in 2002 and has served companies throughout Asia and Australia and across a wide range of industries, particularly financial services, telecommunications, manufacturing and retail. ID/X Partners provides consulting services specializing in leveraging data analytics and decisioning (DAD) solutions combined with risk management and integrated marketing disciplines to help clients optimize portfolio profitability and business processes. The comprehensive consulting services and technology solutions offered by id/x partners make it a one-stop service provider.

**Goals:**  
The goal I want to achieve is to build a prediction model to be able to reduce the risk of defaulting on credit loans that can harm the Company.
 
## Data Dictionary
Column | Description
:---|:---
id | A unique LC assigned ID for the loan listing.
member_id  | A unique LC assigned Id for the borrower member.
loan_amnt | Last month payment was receiveds.
funded_amnt | The total amount committed to that loan at that point in time.
funded_amnt_inv | The total amount committed to that loan at that point in time.
term | The number of payments on the loan. Values are in months and can be either 36 or 60.
int_rate | Interest Rate on the loan.
installment | The monthly payment owed by the borrower if the loan originates.
grade | LC assigned loan grade.
sub_grade | LC assigned loan subgrade.
emp_title | The job title supplied by the Borrower when applying for the loan.
emp_length | Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means ten or more years.
home_ownership | The home ownership status provided by the borrower during registration. Our values are: RENT, OWN, MORTGAGE, OTHER.
annual_inc | The self-reported annual income provided by the borrower during registration.
verification_status | Indicates if the co-borrowers' joint income was verified by LC, not verified, or if the income source was verified.
issue_d | Last month payment was received.
loan_status | Loan payment status.
pymnt_plan | Loan payment plan.
url | URL for the LC page with listing data.
desc | Loan description provided by the borrower.
purpose | A category provided by the borrower for the loan request. 
title | The loan title provided by the borrower.
zip_code | The first 3 numbers of the zip code provided by the borrower in the loan application.
addr_state | The state provided by the borrower in the loan application.
dti | A ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage and the requested LC loan, divided by the borrower’s self-reported monthly income.
delinq_2yrs | The number of 30+ days past-due incidences of delinquency in the borrower's credit file for the past 2 years.
earliest_cr_line | The date the borrower's earliest reported credit line was opened.
inq_last_6mths | The number of inquiries in past 6 months (excluding auto and mortgage inquiries).
mths_since_last_delinq | The number of months since the borrower's last delinquency.
mths_since_last_record | The number of months since the last public record.
open_acc | Number of open trades.
pub_rec | Number of derogatory public records.
revol_bal | Total credit revolving balance.
revol_util | Revolving line utilization rate, or the amount of credit the borrower is using relative to all available revolving credit.
total_acc | The total number of credit lines currently in the borrower's credit file.
initial_list_status | The initial listing status of the loan.
out_prncp | Remaining outstanding principal for total amount funded.
out_prncp_inv | Remaining outstanding principal for portion of total amount funded by investors.
total_pymnt | Payments received to date for total amount funded.
total_pymnt_inv | Payments received to date for portion of total amount funded by investors.
total_rec_prncp | Principal received to date.
total_rec_int | Interest received to date.
total_rec_late_fee | Late fees received to date.
recoveries | Indicates if a payment plan has been put in place for the loan.
collection_recovery_fee | post charge off collection fee.
last_pymnt_d | Last month payment was received.
last_pymnt_amnt | Last total payment amount received.
next_pymnt_d | Next scheduled payment date.
last_credit_pull_d | The most recent month LC pulled credit for this loan.
collections_12_mths_ex_med | Number of collections in 12 months excluding medical collections.
mths_since_last_major_derog | Months since most recent 90-day or worse rating.
policy_code | publicly available policy_code=1; new products not publicly available policy_code=2.
application_type | Indicates whether the loan is an individual application or a joint application with two co-borrowers.
annual_inc_joint | The combined self-reported annual income provided by the co-borrowers during registration.
dti_joint | A ratio calculated using the co-borrowers' total monthly payments on the total debt obligations, excluding mortgages and the requested LC loan, divided by the co-borrowers' combined self-reported monthly income.
verification_status_joint | Indicates if the co-borrowers' joint income was verified by LC, not verified, or if the income source was verified.
acc_now_delinq | The number of accounts on which the borrower is now delinquent.
tot_coll_amt | Total collection amounts ever owed.
tot_cur_bal | Total current balance of all accounts.
open_acc_6m | Number of open trades in last 6 months.
open_il_6m | Number of currently active installment trades.
open_il_12m | Number of installment accounts opened in past 12 months.
open_il_24m | Number of installment accounts opened in past 24 months.
mths_since_rcnt_il | Months since most recent installment accounts opened.
total_bal_il | Total current balance of all installment accounts.
il_util | Ratio of total current balance to high credit/credit limit on all install acct.
open_rv_12m | Number of revolving trades opened in past 12 months.
open_rv_24m | Number of revolving trades opened in past 24 months.
max_bal_bc | Maximum current balance owed on all revolving accounts.
all_util | Balance to credit limit on all trades.
total_rev_hi_lim | Total revolving high credit/credit limit.
inq_fi | Number of personal finance inquiries.
total_cu_tl | Number of finance trades.
inq_last_12m | Number of credit inquiries in past 12 months.

## Methods
This project requires the libraries numpy, pandas, matplotlib, seaborn, sklearn, and imblearn. So, you may need to install these packages if you want to test it.

The process we outline is this:
### **1. EDA**
 - Descriptive Statistics
 - Univariate Analysis
 - Bivariate Analysis
 - Multivariate Analysis

### **2. Preprocessing**
 - Data Cleansing: Check and Handle Missing Value, Type Data, Duplicated, Outliers
 - Feature Encoding: Label Encoding and One Hot Encoding
 - Standardization
 - Class imbalance: over sampling SMOTE

### **3. Modeling** 
I tried 4 types of classification models to see which one is the best at predicting targets, such as:
 - Logistic Regression
 - Random Forest
 - Decission Tree
 - XGBoost

## Result
The following are the results of the model comparison I used:

![Cuplikan layar 2024-03-19 223151](https://github.com/HafiizhTH/credit-risk-prediction/assets/96015981/d90215d3-0264-416a-8fdf-4669d8b1e253)

Based on the prediction model, it can be concluded that the most suitable algorithm is **Random Forest**. This algorithm produces a high ROC_AUC value (1.00), compared to other algorithms that have relatively low values. The selection of the ROC_AUC metric is based on the focus on evaluating how well the model distinguishes between True Positive Rate and minimizes False Negative, especially since class imbalance is handled beforehand, so an appropriate metric is needed for the model to perform well.

From the model results, the best feature importance is as follows: 

![Picture1](https://github.com/HafiizhTH/credit-risk-prediction/assets/96015981/707fc810-4182-4e91-8ca8-4334beaa3f59)


## Business Recommendations
1. Implement a more accurate credit scoring system
> Use statistical models to assess a borrower's credit risk and determine the appropriate interest rate. Then conduct monitoring to understand how well the borrower is meeting his or her repayment obligations.
2. Develop loan products that suit borrowers' needs
> Offer different types of loans, such as short-term loans, long-term loans, and microloans.
