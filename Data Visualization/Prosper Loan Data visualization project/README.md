# (Dataset Exploration Title)
## by (your name here)


## Dataset

>This dataset contains 113,937 rows and 81 columns, most data are in string objects or int type and a few columns are in float type.
before starting i needed to prepare the data for exploring by doing the following:

- Drop unnecessary columns 
- reduce categories in `LoanStatus` column by mergin all Past Due loans to be in one category regardless of the period it has been past due.
- in `IncomeRange` colmun there are some values that are "Not displayed" or "Not Available" i replaced anything that starts with "Not" by "Other" to make them under the "Other" category.
- `Term`,`LoanStatus` , `EmploymentStatus` , `IncomeRange`,`ProsperScore` columns are categorical in str data type i chcanged them to category type.



## Summary of Findings

> This dataset contains a lot of features but before starting i speicified the factors that may have an influence on the loan's outcome status:
><ol>
   <li>Term: The length of the loan expressed in months.</li>
    <li>LoanStatus: The current status of the loan: Cancelled, Chargedoff, Completed, Current, Defaulted, FinalPaymentInProgress, PastDue.</li>
    <li>BorrowerRate: The Borrower's interest rate for this loan.</li>
    <li>ProsperScore: A custom risk score built using historical Prosper data. The score ranges from 1-10, with 10 being the best, or lowest risk score.</li>
    <li>EmploymentStatus: The employment status of the borrower.</li>
    <li>OpenCreditLines: Number of open credit lines.</li>
    <li>IncomeRange: The income range of the borrower.</li>
    <li>TotalProsperPaymentsBilled: Number of on time payments the borrower made on Prosper loans</li>
    <li>LoanOriginalAmount: The origination amount of the loan.</li>
    <li>MonthlyLoanPayment: The scheduled monthly loan payment.</li>

</ol>

observations from Univariate exploration:

> <ol>
    <li>Most loans outcome status are either `Current` or `Completed`.</li>
    <li>The majority of loan borrowers are employed full-time employees in particular.</li>
    <li>From the ProsperScore bar chart it appears that borrowers with prosperScore:`4.0` are more likely to get loans.</li>
    <li>Most loan borrowers prefer 36 months term loans , then 60 months comes in the second place.</li>
    <li>The majority of loan borrowers have from 5 to 10 open credit lines.</li>
    <li>Most borrowers pay 100 per month, some pay up to 300, and very few can pay up to 1000</li>
</ol>

Observations from Bivariate exploration:
<ol>
    <li>There's a relationship between `IncomeRange` and `LoanStatus` as the income decreases the chance of the loan being past due increases.</li>
    <li>Average BorrowerRate incease when the LoanStatus is past due or chargedoff.</li>
    <li>High `LoanAverageAmount`is more likely to be in Past Due `LoanStatus`.</li>
    <li>`OpenCreditLines` number don't have an affect on the `LoanStatus` outcome.</li>
    <li>`Term` does not play a role in predicting `LoanStatus` outcome.</li>
    <li>`TotalProsperPaymentsBilled` can predict the `LoanStatus` outcome, Completed loans seems to have higher total payments, while Past Due loans have less total.</li>
    <li>The higher the average `LoanMonthlyPayment` the more likely it will result in past due.</li>
    <li>`EmploymentStatus` does not affect `LoanStatus` outcome.</li>
    <li>Borrowers with 8.0 `ProsperScore` seem to be the most in Completed status, while borrwers with score 4.0 are the most borrowers with current loans, As for Chargedoff loans borrwers with score 6.0 seem to have the most chargedoff loans.</li>
</ol>


## Key Insights for Presentation

> ><ul>
<li>Both MonthlyLoanPayment and BorrowerRate affect on the LoanStatus the same, as the Monthly payment 
increase it is more likely for the loan to be past due. therefore, increases the borrowerRate.</li>
<li>Borrwers with high  ProsperScore seem to take loans with higher monthly payments which results for them to be charged less BorrowerRate. </li>
</ul>
