# SQL-Projects-for-Data-Analysis

1. Who is the senior most employee based on job title?

--approach 1
select first_name, last_name from employee 
where levels = (select max(levels) from employee)

--approach 2

select first_name, last_name from employee 
order by levels desc
limit 1

2. Which countries have the most Invoices?

--approach 1

select count(*) as count_invoice, billing_country from invoice
group by billing_country
order by count_invoice desc
limit 1

3. What are top 3 values of total invoice?

--approach 1

select total from invoice
order by total desc
limit 3

4. Which city has the best customers? We would like to throw a promotional Music
Festival in the city we made the most money. Write a query that returns one city that
has the highest sum of invoice totals. Return both the city name & sum of all invoice
totals

--approach 1

select billing_city, max(total) as invoice_totals
from invoice
group by billing_city
order by invoice_totals desc
