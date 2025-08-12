# SQL Joins and Nested Queries

This project demonstrates SQL database creation, data insertion, joins, and nested queries using a sample dataset for addresses, customers, and orders.

Database Name
JOINS

Tables
ADDRESSES
Contains address details including street, city, state, and zip code

CUSTOMERS
Stores customer information including name, mobile number, email, and address reference

ORDERS
Stores order details including type of order, associated customer, and delivery address

Database Creation
CREATE DATABASE JOINS
USE JOINS

Table Creation
ADDRESSES table
ADDRESS\_ID INT PRIMARY KEY
STREET VARCHAR(60) NOT NULL
CITY VARCHAR(40) NOT NULL
STATE VARCHAR(40)
ZIP\_CODE VARCHAR(10)

CUSTOMERS table
CUSTOMER\_ID INT PRIMARY KEY
CUSTOMER\_NAME VARCHAR(30) NOT NULL
MOBILE\_NO BIGINT UNIQUE
EMAIL\_ID VARCHAR(40) UNIQUE
ADDRESS\_ID INT NOT NULL FOREIGN KEY REFERENCES ADDRESSES(ADDRESS\_ID)

ORDERS table
ORDER\_ID INT PRIMARY KEY
ORDER\_TYPE VARCHAR(50) NOT NULL
CUSTOMER\_ID INT NOT NULL FOREIGN KEY REFERENCES CUSTOMERS(CUSTOMER\_ID)
ADDRESS\_ID INT NOT NULL FOREIGN KEY REFERENCES ADDRESSES(ADDRESS\_ID)

Sample Data Insertions
Addresses table contains 10 records with various US locations
Customers table contains 10 records each linked to an address
Orders table contains 25 records linked to customers and addresses

Join Queries
Inner Join
Retrieves matching records from both customers and orders

Left Join
Retrieves all customers with matching orders if available

Right Join
Retrieves all orders with matching customers if available

Cross Join
Generates all possible combinations of customers and orders

Self Join
Joins a table to itself to retrieve relational data within the same table

Full Join using Union
Retrieves all records from both customers and orders including unmatched records

Nested Queries
1 Retrieves customers who ordered the alphabetically last order type
2 Retrieves orders placed by customers living in the city with the longest name
3 Retrieves customers who have placed more than two orders
4 Retrieves customers who ordered every order type that customer one has ordered
5 Retrieves the city with the highest number of orders

Purpose
This repository serves as a learning resource for SQL joins and nested queries with practical examples and sample data.
