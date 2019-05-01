# Interest Calculator Lab

> Teacher Note: make sure to walk through computing interest once using simple math (below) before asking students to start the lab. You could also frame this as preparing to do a case study of 3 different students who are each going to choose a different investment strategy.
> 
> **Example:** Imagine you make a $500 investment that returns 10% per year. How much will your original investment be worth after two years?
> 
> **Answer:** After the *first* year of the investment, the original $500 will have grown by 10%. Since 10% of $500 = $50, the investment will now be worth $500 + $50 = $550. In the second year, it will grow by an additional 10%, but now the 10% is of $550 = $55. So at the end of two years, the investment will be worth $550 + $55 = $605.

## Iteration: Annual Investing

1. Write a function to calculate the balance of a zero-interest account in which you deposit $230 each year. What is the balance after 5 years. After 20 years?

```python
def deposit(annual, time):
	# your code here
```

**Answer:** After 5 years of earning no interest, annual additions of $230 would yield 5 x $230 = **$1150**. After 20 years, the amount would be 20 x $230 = **$4600**.

```python
print(deposit(230, 5))
# 1150

print(deposit(230, 20))
# 4600
```

But what if you earned money every month or year that you keep that money invested? The computations below will calculate how much money you would have given three variables:

- an initial `investment`
- an interest `rate`
- an amount of `time`

2. Write a function that will help you compute how much money you would have after 1 year if you invest a given amount in an account with a particular annual return.

> Note: there's no need for iteration here, but try to use lots of named variables and print functions.

```python
def invest(initial, rate, time):
	# your code here
```

**Example:** After 1 year, an original $632 investment growing at 6% per year will have grown by 6%. Since 6% of $632 = $37.92, the investment will be worth $632 + $37.92 = **$669.92**.

**Alternate Solution:** After 1 year, the value of the investment will be 106% of the original investment since it will be worth the original 100% plus the additional 6%. 106% is the same as multiplying by 1.06, so the investment would be worth 1.06 * $632 = **$669.92**.

```python
print(invest(632, 6, 1))
# 669.92
```

3. Update the `invest()` function to leverage the `time` parameter in order to calculate the value of an investment growing at a particular annual rate for 10 or more years.

**Example:** After 10 years, an initial $632 investment growing at 6% per year would be worth **$1131.82**.

> Note: Since the result is currency, try to see if you can round your answer to two decimal places.

```python
print(invest(632, 6, 10))
# 1131.82
```

4. Use your `invest()` function to compute the value of:
	1. A $5,000 investment at 3% for 10 years.
	2. A $10,000 investment at 3% for 5 years. (double the amount, half the time)
	3. A $2,500 investment at 3% for 20 years. (half the amount, double the time)

5. Use your `invest()` function to compute the value of:
	1. A $4,000 investment at 5% for 30 years.
	2. A $4,000 investment at 7.5% for 30 years.
	3. A $4,000 investment at 10% for 30 years.

## Iteration: Periodic Investing

Usually, investors don't just make an investment and sit on it for a long time. Instead, they will frequently continue to deposit money into the investment account in order to compound the effect of the interest growth.

Imagine three investors: Clara, Jerome, and Z.

Clara starting thinking about investing when she turned 20, so that year she invested $1,000 into an account that earns 5% annually. She was able to continue to invest $1,000 a year for the next 9 years until she turned 30. That year she could no longer invest the $1,000 per year, but she also didn't need to touch her investments so she just let them grow.

Jerome was a bit later to the game. At age 30, he invested $1,000 in the same fund that Clara uses, so his money also earns 5% annually. But Jerome has done well, so plans to continue to add $1,000 every year to his investment.

Z was somewhere in between Clara and Jerome. Z thought about investing when they turned 25 and also invested in the same fund that Clara and Jerome used, earning 5% annually. But Z invested $800 initially, and then planned to add $800 every year for the rest of their life.

6. Who has more money in their account at age 45? At age 50? At age 65?

Update your `invest()` function to account for these two new factors:

- Annual contributions
- A period of contributions followed by no contributions

> JOLSON: I THINK THE MESSAGE OUGHT TO BE START EARLY AND CONTINUE MAKING SMALL CONTRIBUTIONS IF THAT'S ALL YOU CAN DO. THOUGHTS?

## Types of Investments

Consider the following three types of investment accounts:

- **Stocks**: Stocks are investments in a particular company which - depending on how that company performs - might generate several thousand percent yields or might completely crash with a -100% yield (losing all of your money in the process).
- **Index Funds**: Index funds are investments in a type of mutual fund that bring together several other funds with the goal of matching (or tracking) one of the financial market indexes, e.g. the S&P 500. These funds tend to be less volatile than a given stock, but can still gain or lose money.
- **Bonds**: Bonds are investments which have a fixed-rate of income over a period of time, and the bond issuer is obligated to pay the amount of the bond at a specified future date, e.g. in 20 years. Bonds tend to have lower yields than stocks or index funds, but they are also very low risk.

7. Create three new functions: `stock()`, `indexFund()`, and `bond()`. Each function should take two inputs, `initial` investment and `time` of the investment.

```python
def stock(initial, time):
	# Your code here

def indexFund(initial, time):
	# Your code here

def bond(initial, time):
	# Your code here
```

- The `stock()` function should compound interest at a random rate (between -100% and 100%).
- The `indexFund()` function should compound interest at a rate similar to the growth of the S&P 500 over the same period of time.
	> Use historical data you find online to calculate this rate.
- The `bond()` function should compound interest at 2% per year.

How do the three functions compare when given the same `initial` investment and length of `time`? 

## Monthly Interest

Many investments will compound interest monthly instead of annually, however the monthly rate is only 1/12th of the annual rate.

8. Create a new method called `monthly()` that takes three parameters: an `initial` investment, an *annual* interest `rate`, and a length of `time` in years.

> Note: Your function should convert the *annual* interest `rate` into a monthly rate, and the `time` in years to a number of months.

```python
def monthly(initial, rate, time):
	# Your code here
```

Compare your original `invest()` function to your new `monthly()` function. Which way of compounding interest will make you the most money for a given period of time?

## Student Loans

We can use the same types of functions to calculate how long it will take to pay down debts and to compare how different payment strategies will affect the total amount paid to lenders.

Consider three students, each of whom borrowed a student loan of $30,000 in order to pay for school. The loan company charges a 5% annual interest rate, which means that if left unpaid, the amount the student owes following graduation will grow by 5% every year. The loan company has set a $200 minimum that must be paid back each month, but a student can defer paying that amount for up to ten years. During the ten years, however, the 5% interest is still applied annually.

The three students have different strategies for how to pay back their loan:

- Upon graduation, Sage begins to make the minimum payments necessary as required by the loan company.
- Steve defers making any payments for 5 years, after which he makes payments of $400 per month.
- Upon graduation, Sid pays $300 per month in an attempt to pay off the loan faster.

9. Compare the three payment strategies to determine how much each graduate will end up paying to the loan company.

Which strategy did you think would be best, and which did you calculate as the most cost-effective?

## Credit Cards

You may not think of credit card debt as taking out a loan, but that's essentially what you're doing. The same interest-bearing types of calculations can be used to calculate how much things cost when bought on credit.

10. Assume your credit card has an *annual* interest rate of 12%. Calculate the *actual* cost of a $1,200 mattress if you pay:

- $50 per month
- $100 per month
- $200 per month

11. Consider the following two debts:

- You owe a credit card company $2,000 and they charge a 22% annual interest rate.
- You owe a student loan company $20,000 and they charge a 6% annual interest rate.

If you have $400 per month to pay down debts, which debt should you pay down first? How much would you save by paying that debt first instead of the other debt?
