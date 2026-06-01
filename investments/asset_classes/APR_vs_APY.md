# APR vs APY

This document covers the definitions of APR and APY, contrasts the two, and discusses when each is likely to be provided.


## APR - Annual Percentage Rate

The Annual Percentage Rate (APR) is an attempt at combining fees and interest into an single rate for apples-to-apples comparisons between lenders.  The authoritative source seems to be [the Consumer Financial Protection Bureau (CFPB)](https://www.consumerfinance.gov/rules-policy/regulations/1026/14/), where the APR is defined according to the following:
- the actual APR must be within a tolerance of 1/8th of 1% (i.e., 0.125%) above or below the stated value
- multiply the periodic rate by the number of periods in a year (with options for handling multiple periods with differing rates)
- including minimum balance charges or flat fees in the APR for the billed period (see details with the interpretation of 14(c)(2))
- including transaction charges, weighted by the amount incurring the charge (e.g., $50/$1000 for a $50 charge on a $1000 loan)

There's a lot going on here, and the full writeup is worth attempting to parse.  At its core, there appears to be two components, as illustrated across several other non-legal references (e.g., [Investopedia](https://www.investopedia.com/terms/a/apr.asp) as in [Capital One](https://www.capitalone.com/learn-grow/money-management/how-to-calculate-apr-on-credit-card/))
- calculate an effective rate as the sum of interest rate charged over a compounding period and the total fees charged directly by the lender divided by the principal lent
- convert this figure to an effective yearly rate, by dividing the fee contribution by the number of years in the loan.  For loans shorter than a year, we instead convert to a yearly basis by multiplying over the number of interest/fee periods in a year where these charges are incurred.

I've struggled to find an explicit example of the APR being calculated from an authoritative source.  That said, it appears to involve combining a simple interest portion of the loan with an annualized (still, not compounding) calculation of the fees.  For example, my understanding is that a \$100 loan over 30 days, charging 2% interest over the period, and costing an additional \$3 in fees would produce an APR according to the following:  
$\text{APR} = \left( .02 + \frac{\$3}{\$100} \right) \times \frac{365 \text{ days}}{30 \text{ days}} \times 100 \% = \frac{365 \text{ days}}{30 \text{ days}}\times 5\% \approx 60.83\% \quad .$  
Consider, alternatively, another \$100 loan over 3 years, charging 2% interest per year, and costing an additional \$3 in fees; this would produce an APR as:  
$\text{APR} = \left( 3\times 2\% + \frac{\$3}{\$100} \times 100\% \right) \times \frac{1 \text{ year}}{3 \text{ years}} = \frac{9}{3} \% = 3\% \quad . $  
In this last case, \$3 is 3\% of \$100, but is spread out over the 3 year loan to only contribute an additional 1\% to the resulting APR.


### Downsides

The APR misses some fees not directly to the lender, like attorneys fees if necessary, neglects compounding of interest over the term, and is complex to calculate.  Even if fees are neglected, compounding will lead to a difference in the actual interest paid and the stated APR.  For example, if a loan compounds monthly at 1% interest, the APR for this loan is:  
$\text{APR} = 12 \times 1\% = 12\%\quad .$  
Of course, if you actually have this loan, and make no payments, the monthly compounding over a year would result in actual interest due of  
$\text{Total interest} = \left( 1 + 0.01 \right)^{12} \approx 1.127 \quad ,$  
or nearly 12.7% accrued interest over a year, even without considering fees.

For a given rate $r$, the stated APR and the actual interest accrual due to compounding could be off by at most the difference between yearly compounding and continuous compounding, ignoring fees.  At yearly compounding, the actual interest cost and the APR would be equal.  For continuous compounding, the annualized interest rate $r_y$ would be  
$r_y = e^r - 1 \quad ,$  
which is strictly greater than $r$ (e.g., consider the Taylor expansion around $r=0$).  The two will be similar for very small interest rates (e.g., 0.01, or 1%), end diverge _exponentially_ for larger ones.


## APY - Annual Percentage Yield

The APY is typically provided for investments, and is meant to convey how much the buyer receives over the course of a year based on their investment.  The APY is actually quite straightforward as the annualized rate of return on an investment including compounding, _but_ neglecting fees.  For example, if a savings account pays 1% interest per month on the current balance in an account, this is monthly compounding at 1%, and results in an APY of:  
$\text{APY} = \left[ \left( 1 + 0.01 \right)^{12} - 1 \right] \times 100\% \approx 12.68\% \quad .$  


### Downsides

The APY is an interesting complement to the APR, in that it includes compounding but neglects fees.  


## Comparing APR vs. APY

Lenders are required to provide the APR, and the lack of compounding typically makes low-fee loans look more appealing through their APR.  The APY is typically provided by companies selling an investment product, such as a bank CD, and emphasizes the compounding to show the largest possible rate (the interest when equivalently compounded annually) to prospective customers.  The APR at least includes fees, but requires additional math to understand the true cost of interest, particularly for high-interest loans (e.g., credit cards, payday loans, etc.) where even monthly compounding results in significant contributions over a year.  The APY demonstrates compounding, but misses fees and still requires additional research to understand the compounding schedule (e.g., whether an investment must be held for a day, a month, or a year to receive the expected APY).