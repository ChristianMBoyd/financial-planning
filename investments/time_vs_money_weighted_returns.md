# Time-weighted vs. money-weighted investment returns

This document analyzes the difference between time-weighted, money-weighted, and the simple rate of return when judging investment performance.

## Simple rate of return

The simple rate of return is the proportionate increase or decrease in the investment from its original value to its current value, ignoring any cash inflows or outflows over the investment period.  For a one-time lump sum investment, this makes sense; however, a dollar-cost averaged investment will show increases from both regular deposits and investment returns in the same simple rate of return.

Notably, this value is _not_ a compounded annual growth rate, but an absolute relative return.


## Time-weighted return

The time-weighted rate of return compounds the relative returns of an investment over its life, segmenting investment periods before and after any deposits or withdrawals.  The goal of the time-weighted return is to gauge the performance of the investment strategy (or investment manager), rather than to account for the realized monetary gain resulting from a particular investment account.


## Money-weighted return

The money-weighted return is equivalent to the internal rate of return, which is the discount rate at the time of the initial investment that makes all cash flows equal to the final investment value.  This is tricky and I have seen somewhat garbled wording [in the Wikipedia page](https://en.wikipedia.org/wiki/Rate_of_return#Money-weighted_rate_of_return); this seems most clear from [a concrete stackexchange answer](https://money.stackexchange.com/a/26469), [an Investopedia article](https://www.investopedia.com/terms/m/money-weighted-return.asp), and common sense.  There are a few ways of writing the formula for the internal rate of return, where I'll start with the basic one, which is that the present value (at the time of the initial investment) of all inflows and outflows from the investment porfolio must equal 0 when the final invesment value is included as an outflow.  I.e.,  
### $\sum_{n = 0}^N\frac{C_n}{\left( 1 + r \right)^{t_n}} = 0 \quad ,$  
where $C_n$ enumerate all cash flows considering withdrawals as positive and deposits as negative ($C_0 < 0$ is the initial investment, $C_N > 0$ is the present-day value of the investment portfolio) and $t_n$ enumerate the (annualized) periods relative to the initial investment.  Dividends can be considered on their own, but have vanishing net contribution so long as they are immediately invested (positive dividend payment, negative re-investment of the same amount).  Equivalently, the discounted value of all deposits must equal the discounted value of all withdrawals (where $C_N$, the present value of the portfolio, is treated as a withdrawal):  
### $\sum_{n\in\lbrace\text{deposits}\rbrace} \frac{|C_n|}{\left( 1 + r \right)^{t_n}} = \sum_{m\in\lbrace\text{withdrawals}\rbrace} \frac{|C_m|}{\left( 1 + r \right)^{t_m}} \quad ,$  
where only positive quantities are considered as the two kinds of cash flows are already collected on either side of the equality.  A third way to look at this is to collect terms based on portoflio value accumulation, such as  
### $|C_0| + \sum_{n\in\lbrace\text{deposits after initial}\rbrace} \frac{|C_n|}{\left( 1 + r \right)^{t_n}} - \sum_{m\in\lbrace\text{withdrawals}\rbrace} \frac{|C_m|}{\left( 1 + r \right)^{t_m}} = \frac{|C_N|}{\left( 1 + r \right)^{t_N}}  \qquad .$  

In any case, the money-weighted rate of return is sensitive to _when_ deposits and withdrawals were made, and acts as a judge of market (or investment) timing.