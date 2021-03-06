# Portfolio Project 1
## Sales_PowerBi

### **Shows record of Market** 
![sales of Atliq 1](https://user-images.githubusercontent.com/93612190/140888359-dd88a46c-1487-4e38-aeff-c0ea779fa770.png)

### **Record of Transactions**
![sales of Atliq 2](https://user-images.githubusercontent.com/93612190/140888705-7fdd2cba-e936-4f58-8997-074f53ec56dd.png)


### **Joined Tables usig Inner Join**
![sales of Atliq 3](https://user-images.githubusercontent.com/93612190/140891054-c60e05f8-131b-44df-9e99-5a81bf69b697.png)

## Data Analysis Using SQL

Show all customer records

`SELECT * FROM customers;`

Show total number of customers

`SELECT count(*) FROM customers;`

Show transactions for Chennai market (market code for chennai is Mark001

`SELECT * FROM transactions where market_code='Mark001';`

Show distrinct product codes that were sold in chennai

`SELECT distinct product_code FROM transactions where market_code='Mark001';`

Show transactions where currency is US dollars

`SELECT * from transactions where currency="USD"`

Show transactions in 2020 join by date table

`SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

Show total revenue in year 2020,

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`

Show total revenue in year 2020, January Month,

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

Show total revenue in year 2020 in Chennai

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";`

## Data Analysis Using Power BI
### Formula to create norm_amount column
`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`

## **Data is Loaded in PowerBI Desktop** 
![powerbi](https://user-images.githubusercontent.com/93612190/140901392-9f83c483-fff1-45e1-be4a-d10ccd2a32eb.png)


## **Data Model showing the relation**
![data model powerbi](https://user-images.githubusercontent.com/93612190/140901639-591b01cf-6006-49ce-865c-30aca1446798.png)



##  **ETL process in Power Query Editor**
![powerQuery power bi](https://user-images.githubusercontent.com/93612190/140901671-f12ff64a-dc1f-4146-bce2-1261610afea0.png)



## **Finalised Dashboard for Stakeholders**
![Dashboard power bi](https://user-images.githubusercontent.com/93612190/140901735-e0b391e2-fb78-4b11-917c-0512284be9cd.png)







