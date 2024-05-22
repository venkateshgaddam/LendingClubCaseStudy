# Lending Club Case Study

Lending Club, a finance company serving urban customers, must refine its loan approval strategy. The goal is to make smart choices and avoid money loss, mainly from high-risk loans.

These losses, known as credit losses, happen when borrowers don’t repay their loans, with the worst cases being “charged-off” borrowers.

The main goal is to help Lending Club reduce these losses. This involves two key points:

1. It’s vital to identify borrowers who will repay their loans, as they bring in profit through interest. Turning away these borrowers means missing out on potential income.
2. Approving loans for those unlikely to repay, risking default, can lead to significant financial setbacks.

## Table of Contents
* [Problem Statement](#Problem-Statement)
* [Objectives](#objectives)

* [Important Columns](#important-columns)
* [Column Format](#convert-column-format)
* [Column Values](#convert-column-values)

* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

## Problem Statement

You work for a consumer finance company which specialises in lending various types of loans to urban customers. When the company receives a loan application, the company has to make a decision for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:

If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company

If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company

The data given below contains information about past loan applicants and whether they ‘defaulted’ or not. The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.

In this case study, you will use EDA to understand how consumer attributes and loan attributes influence the tendency of default.

## Objectives
This company is the largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. Borrowers can easily access lower interest rate loans through a fast online interface. 

Like most other lending companies, lending loans to ‘risky’ applicants is the largest source of financial loss (called credit loss). Credit loss is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed. In other words, borrowers who default cause the largest amount of loss to the lenders. In this case, the customers labelled as 'charged-off' are the 'defaulters'.

If one is able to identify these risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA is the aim of this case study.

In other words, the company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment.

To develop your understanding of the domain, you are advised to independently research a little about risk analytics (understanding the types of variables and their significance should be enough).

## Important Columns
The given columns are leading attributes, or **predictors**. These attributes are available at the time of the loan application and strongly helps in **prediction** of loan pass or rejection. Key attributes *Some of these columns may get dropped due to empty data in the dataset*
* **Customer Demographics**
  * Annual Income (annual_inc) - Annual income of the customer. Generally higher the income, more chances of loan pass.
  * Home Ownership (home_ownership) - Wether the customer owns a home or stays rented. Owning a home adds a collateral which increases the chances of loan pass.
  * Employment Length (emp_length) - Employment tenure of a customer (this is overall tenure). Higher the tenure, more financial stablity, thus higher chances of loan pass
  * Debt to Income (dti) - The percentage of the salary which goes towards paying loan. Lower DTI, higher the chances of a loan pass.
  * State (addr_state) - Location of the customer. Can be used to create a generic demographic analysis. There could be higher delinquency or defaulters demographicaly.
* **Loan Attributes**
  * Loan Ammount (loan_amt)
  * Grade (grade)
  * Term (term)
  * Loan Date (issue_date)
  * Purpose of Loan (purpose)
  * Verification Status (verification_status)
  * Interest Rate (int_rate)
  * Installment (installment)
  * Public Records (public_rec) - Derogatory Public Records. The value adds to the risk to the loan. Higher the value, lower the success rate.
  * Public Records Bankruptcy  (public_rec_bankruptcy) - Number of bankruptcy records publocally available for the customer. Higher the value, lower is the success rate.

## Convert Column Format
- `(loan_amnt, funded_amnt, funded_amnt_inv)` columns are Object and will be converted to float
- `(int_rate, installment, dti)` columns are Object and will be converted to float
- **strip "month"** text from `term` column and convert to integer
- Percentage columns `(int_rate)` are object. **Strip "%"** characters and convert column to float
- `issue_d` column **converted to datetime format**

## Convert Column Values 
- `emp_length` converted to integer with following logic. Note < 1 year is converted to zero and 10+ converted to 10.
    - < 1 year: 0,  
    - 2 years: 2,  
    - 3 years: 3,  
    - 7 years: 7,  
    - 4 years: 4,
    - 5 years: 5,
    - 1 year: 1,
    - 6 years: 6,
    - 8 years: 8,
    - 9 years: 9,
    - 10+ years: 10

## Conclusions
- Do not issue loans for users with Grades D, E, F, and G
- Implement Stricter risk assessment criteria for users with Grades B, C, and D
- Avoid giving loan to small businesses
- Mortgage seems profitable. Hence, we can give loans for lesser interest to attract more applicants.
- Giving out loan for a term of 36 months seems far more profitable
- Evaluate the risk of 60-month loans and consider limiting the maximum term or adjusting interest rates
- Prioritize applicants with higher annual incomes for loan approval
- Income range of 0-40K have the highest risk, hence consider adjusting interest rates for those applicants

## Technologies Used
- Python - version 3.12.2
- numpy - version 1.26.4
- pandas - version 2.2.2
- matplotlib - version 3.8.4
- seaborn - version 0.13.2


## Acknowledgements
- This project created as part of Upgrad's Machine Learning & AI course

## Contact
Created by [@venkateshgaddam](https://github.com/venkateshgaddam) and [@varsim91](https://github.com/varsim91) - feel free to contact me!
