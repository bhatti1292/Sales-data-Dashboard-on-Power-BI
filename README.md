# POWERBI-Project
# I have used MYSQL to get insights of the data.
I have used MYSQL to get insights of the data.
1. Join two tables from the data set named sales when the year is 2020.
SELECT sales.transactions.*,sales.date.*
FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date
WHERE sales.date.year=2020;
2.  Generating total revenue in 2019.
SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date
WHERE sales.date.year=2019;
3. Total revenue generated during the year 2020 when the market code is Mark001.
SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date
WHERE sales.date.year=2020 AND sales.transactions.market_code="Mark001";
4. This code will show the distinct product_code when market code is Mark001.
SELECT distinct product_code FROM sales.transactions WHERE market_code="Mark001";
# In POWERBI I have performed ETL and data cleaning to make the data clean
# The code that I used to create a column names norm_sales_amount is as follows.
= Table.AddColumn(clean_up_currency, "norm_sales_amount", each if [currency] = "USD#(cr)" then [sales_amount]*80 else [sales_amount])
# You can have a look on my final dashboard by looking at the picture below
![image](https://user-images.githubusercontent.com/116423607/227150703-6690ed18-2827-4c1f-b670-761e1500570b.png)


