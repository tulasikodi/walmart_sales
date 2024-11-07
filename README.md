## Overview
This readme file provides an overview of the data analysis conducted on Walmart sales data using SQL SERVER and SQL SERVER.
The analysis involves creating a database, performing various SQL queries, and conducting feature engineering to gain insights into the sales data.

## Table of Contents

## Table of Contents
- [Product Insights](#product-insights)
- [Sales Insights](#sales-insights)
- [Customer Insights](#customer-insights)

## Purposes Of The Project

The major aim of thie project is to gain insight into the sales data of Walmart to understand the different factors that affect sales of the different branches.



## about database


| Column                  | Description                       | Data Type         |
|-------------------------|-----------------------------------|-------------------|
| invoice_id              | Invoice of the sales made        | VARCHAR(30)       |
| branch                  | Branch at which sales were made  | VARCHAR(5)        |
| city                    | The location of the branch       | VARCHAR(30)       |
| customer_type           | The type of the customer         | VARCHAR(30)       |
| gender                  | Gender of the customer making purchase | VARCHAR(10) |
| product_line            | Product line of the product sold | VARCHAR(100)      |
| unit_price              | The price of each product        | DECIMAL(10, 2)    |
| quantity                | The amount of the product sold   | INT               |
| VAT                     | The amount of tax on the purchase| FLOAT(6, 4)       |
| total                   | The total cost of the purchase   | DECIMAL(10, 2)    |
| date                    | The date on which the purchase was made | DATE     |
| time                    | The time at which the purchase was made | TIMESTAMP |
| payment_method          | Payment method used              | VARCHAR(15)       |
| cogs                    | Cost of Goods Sold               | DECIMAL(10, 2)    |
| gross_margin_percentage | Gross margin percentage          | FLOAT(11, 9)      |
| gross_income            | Gross Income                     | DECIMAL(10, 2)    |
| rating                  | Rating                           | FLOAT(2, 1)       |


# Analysis List
### 1.Product Analysis
Conduct analysis on the data to understand the different product lines, the products lines performing best and the product lines that need to be improved.

### 2. Sales Analysis
This analysis aims to answer the question of the sales trends of product. The result of this can help use measure the effectiveness of each sales strategy the business applies and what modificatoins are needed to gain more sales.

### 3. Customer Analysis
This analysis aims to uncover the different customers segments, purchase trends and the profitability of each customer segment.

## APPROACH USED
 
### 1.  Data Wrangling: 
 This is the first step where inspection of data is done to make sure NULL values and missing values are detected and data replacement methods are used to replace, missing or NULL values.
Build a database
Create table and insert the data.
Select columns with null values in them. There are no null values in our database as in creating the tables, we set NOT NULL for each field, hence null values are filtered out.

### 2. Feature Engineering: This will help use generate some new columns from existing ones.
1. Added a new column named time_of_day to give insight of sales in the Morning, Afternoon and Evening.
   This will help answer the question on which part of the day most sales are made.

3. Added a new column named day_name that contains the extracted days of the week on which the given transaction took place (Mon, Tue, Wed, Thur, Fri). This will help answer the question on which week of the day each branch is busiest.
   
5. Added a new column named month_name that contains the extracted months of the year on which the given transaction took place (Jan, Feb, Mar). Help determine which month of the year has the most sales and profit.


### 3. Exploratory Data Analysis (EDA): Exploratory data analysis is done to answer the listed questions and aims of this project.


## Business Questions To Answer

#### Product  Insights
1. How many unique product lines does the data have?
2. What is the most common payment method?
3. What is the most selling product line?
4. What is the total revenue by month?
5. What month had the largest COGS?
6. What product line had the largest revenue?
7. What is the city with the largest revenue?
8. What product line had the largest VAT?
9. Fetch each product line and add a column to those product lines showing "Good" or "Bad". Mark as "Good" if sales are greater than the average sales.
10. Which branch sold more products than the average product sold?
11. What is the most common product line by gender?
12. What is the average rating of each product line?

#### Sales Insights
1. Number of sales made at each time of day per weekday.
2. Which customer type brings in the most revenue?
3. Which city has the highest VAT (Value Added Tax) percentage?
4. Which customer type pays the most in VAT?

#### Customer Insights
1. How many unique customer types does the data have?
2. How many unique payment methods does the data have?
3. What is the most common customer type?
4. Which customer type buys the most?
5. What is the most common gender of customers?
6. What is the gender distribution per branch?
7. Which time of the day receives the most customer ratings?
8. Which time of the day receives the most customer ratings per branch?
9. Which day of the week has the highest average ratings?
10. Which day of the week has the highest average ratings per branch?


## database creation

```sql
create database if not exists salesDataWalmart;

create table if not exists sales (
     invoice_id varchar(30) not null primary key,
     branch varchar (5) not null,
     city varchar(30) not null,
     customer_type varchar(30) not null, 
     gender varchar(30) not null,
     product_line varchar(100) not null,
     unit_price decimal(10,2) not null,
     quantity int not null,
     VAT float(6,4) not null,
     total decimal(12,4) not null,
     date datetime not null,
     time TIME not null,
     payment_method varchar(15) not null,
     cogs decimal(10,2) not null,
     gross_margin_pct float(11,9),
     gross_income decimal(12,4),
     rating float(2,1)
);
```


