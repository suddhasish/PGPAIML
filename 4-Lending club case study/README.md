# Lending Club Case_Study
> Understanding Loan Risk Analytics in for a consumer finance using Exploratory Data Analysis (EDA).

**Business Understanding:**
You work for a consumer finance company Lending Club  which specialises in lending various types of loans to urban customers. 
When the company receives a loan application, the company has to make a decision for loan approval based\ on the applicant’s profile. Two types of risks are associated with the bank’s decision:

If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company \

If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company \

The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher \


**Business Objectives:**

This company is the largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. Borrowers can easily access lower interest rate loans through a fast online interface. \\

Like most other lending companies, lending loans to ‘risky’ applicants is the largest source of financial loss (called credit loss). Credit loss is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed. In other words, borrowers who default cause the largest amount of loss to the lenders. In this case, the customers labelled as 'charged-off' are the 'defaulters'. \\

If one is able to identify these risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA is the aim of this case study. \

In other words, the company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment. interest rate,etc.




## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
 This project involves a detailed exploratory data analysis (EDA) on a loan dataset to identify patterns 
`that indicate a likelihood of default among loan applicants.


  The background of this project: This is rooted in risk analytics within the financial services sector, particularly in consumer finance.
  
  business problem:  addresses the challenge of loan approval decisions and the associated risks of financial loss due to defaulting customers.

  dataset:  contains information about past loan applicants and their loan repayment status, including whether they defaulted or not.

The analysis aims to provide insights that could help in making informed decisions on loan approvals to minimize financial risks and losses.
- Understanding the factors that contribute to loan defaults is crucial for the company to adjust its risk assessment models and lending practices.
- By analyzing various attributes of loan applicants and their loan history, the project seeks to uncover trends and patterns that could predict default   behavior.
- The project also explores the impact of loan terms, interest rates, and borrower demographics on loan repayment.
- Insights derived from this analysis will inform the development of strategies to mitigate risks associated with loan defaults.
- Additionally, the project examines external economic factors that could influence borrower default rates and loan performance.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions

- Loan Grade: Lower-grade loans (G, F, E, D) are more susceptible to defaults, suggesting a need for stricter lending criteria or higher interest rates for these loans.
- Loan Purpose: Loans intended for small businesses, credit cards, and debt consolidation show higher default rates, indicating these loan purposes should be monitored closely.
- Revolving Utilization: High revolving utilization rates significantly increase the risk of default, pointing to the importance of considering credit utilization as a factor in loan approval processes.
- Credit Line Age: Newer credit lines are more frequently associated with charged-off loans, suggesting that the age of credit history should play a more significant role in risk assessment.
- Late Payments and Last Payment Amount: Indicators such as late payments and lower last payment amounts correlate with higher default rates, highlighting the need for early intervention strategies to address late payments.

- Enhanced Scrutiny for Certain Loans: Borrowers with fluctuating incomes are more likely to default, indicating that stability of income should be a key consideration in the loan approval process.
  Finally, the study suggests that enhancing data collection on borrower behavior and external economic conditions can improve predictive models of loan default.
- Loans falling into lower grades, or for purposes like small business, should be subjected to more rigorous evaluation.

- Interest Rate Adjustments: Consider adjusting interest rates based on revolving utilization and credit line age to mitigate risks.

- Monitoring Late Payments: Close monitoring of late fees and last payment amounts can provide early warning signs of potential defaults.

- Recovery Rate by Housing Situation: Higher recovery rates are noted for customers who rent or have rent or mortgages which mean this type of customer tend to default more.

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used
- Python - version 3.11.5
- NumPy - version 1.26.4
- Pandas - version 2.2.2
- Matplotlib - version 3.8.4
- Seaborn - version 0.13.2

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
This is a Group Case Study done as a part of Executive PG Programme in AI & ML from IIIT, Bangalore by upGrad.

Batch: ML C65

- This project was inspired by real-world business scenarios in the financial sector dealing with credit risk.
- Gratitude goes to the open-source community for making the technologies used in this project accessible.


## Contact
Created by [@suddhasish] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->