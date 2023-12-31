# Sales-Insights-Tableau


## Overview
The purpose of the project is Unlocking sales insights using tableau for decision support and automate it to reduce the time required for data gathering.
The final product is an automated dashboard providing quick and latest sales insights in order to support data driven decision making.


## To use the Sales Insight dashboard:
1. Open the Tableau workbook in Tableau Desktop or Tableau Online.
2. Navigate to the "Dashboard" tab for a comprehensive view of sales insights.
3. Filter data using the provided filters for a more targeted analysis.
4. Explore different sheets for detailed visualizations and trends.

## Data Source

SQL database dump is in db_dump.sql file above. Download db_dump.sql file to your local computer and import it.

## Data Analysis Using SQL
Show all customer records

SELECT * FROM customers;

Show total number of customers

SELECT count(*) FROM customers;

Show transactions for Chennai market (market code for chennai is Mark001

SELECT * FROM transactions where market_code='Mark001';

Show distrinct product codes that were sold in chennai

SELECT distinct product_code FROM transactions where market_code='Mark001';

Show transactions where currency is US dollars

SELECT * from transactions where currency="USD"

Show transactions in 2020 join by date table

SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

Show total revenue in year 2020,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

Show total revenue in year 2020, January Month,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

Show total revenue in year 2020 in Chennai

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";
