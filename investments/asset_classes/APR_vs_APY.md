# APR vs APY

This document covers the definitions of APR and APY, contrasts the two, and discusses when each is likely to be provided.


## APR - Annual Percentage Rate

The Annual Percentage Rate (APR) is an attempt at combining fees and interest into an single rate for apples-to-apples comparisons between lenders.  The authoritative source seems to be [the Consumer Financial Protection Bureau (CFPB)](https://www.consumerfinance.gov/rules-policy/regulations/1026/14/), where the APR is defined according to the following:
-


The interest rate part of the APR follows a very simple formula that mocks the annualized rate, without specifying the compounding schedule.  For a given rate over a period, the APR is simply rate per period times the number of periods in a year.  For example, if a loan compounds monthly at 1% interest, the APR for this loan is:  
$\text{APR} = 12 \times 1\% = 12\%\quad .$  
Of course, if you actually have this loan, and make no payments, the monthly compounding over a year would result in actual interest due of  
$\text{Total interest} = \left( 1 + 0.01 \right)^{12} \approx 1.127 \quad ,$  
or nearly 12.7% accrued interest over a year, even without considering fees.

For a given rate $r$, the stated APR and the actual interest accrual due to compounding could be off by at most the difference between yearly compounding and continuous compounding, ignoring fees.  At yearly compounding, the actual interest cost and the APR would be equal.  For continuous compounding, the annualized interest rate $r_y$ would be  
$r_y = e^r - 1 \quad ,$  
which is strictly greater than $r$ (e.g., consider the Taylor expansion around $r=0$).  The two will be similar for very small interest rates (e.g., 0.01, or 1%), end diverge _exponentially_ for larger ones.


### Incorporating fees

