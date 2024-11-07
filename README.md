## Overview
This readme file provides an overview of the data analysis conducted on Walmart sales data using SQL SERVER and SQL SERVER.
The analysis involves creating a database, performing various SQL queries, and conducting feature engineering to gain insights into the sales data.

## Table of Contents

## Database Creation

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
