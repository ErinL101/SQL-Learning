1. Inner Joins
combine the columns in different table

`INNER JOIN` = `JOIN` ( INNER is optional)
```
SELECT *
FROM orders
JOIN customers 
	ON orders.customer_id = customers.customer_id
```
ON + a condition


```
SELECT 
     customer_id❌, order_id, first_name, last_name
FROM orders
JOIN customers
      ON orders.customer_id = customers.customer_id
```
Both tables have a customer_id column, so MySQL doesn't know which table the column comes from.
--> When the same column exists in multiple tables, qualify the column by prefixing it with the table name.

```
SELECT 
     orders.customer_id✔, order_id, first_name, last_name
FROM orders
JOIN customers
      ON orders.customer_id = customers.customer_id
```


Using aliases for tables to simplify the code
```
SELECT o.customer_id, order_id, first_name, last_name
FROM orders o
JOIN customers c
	ON o.customer_id = c.customer_id
```
!o.customer_id <- When using an alias, use the alias consistently throughout the query.

*Ex
```
SELECT oi.product_id, order_id, name, quantity, oi.unit_price
FROM order_items oi
JOIN products p
	ON oi.product_id = p.product_id
```
oi.unit_price is different to p.unit_price in this case

2. Join Across Databases
```
USE sql_store
;
SELECT *
FROM order_items oi
JOIN sql_inventory.products p
	ON oi.product_id = p.product_id
```
only have to prefix the table that are not at current database  

3.Self Joins  
```
USE sql_hr
;
SELECT 
	e.employee_id,
    e.first_name,
    m.first_name AS manager
FROM employees e
JOIN employees m
	ON e.reports_to = m.employee_id
```
Joining a table with itself → use different aliases and prefix each column with alias.

4. Joining Multiple Tables
```
USE sql_store
;
SELECT 
	o.order_id, o.order_date, 
    c.first_name, c.last_name,
    os.name AS status
FROM orders o
JOIN customers c
	ON o.customer_id = c.customer_id
JOIN order_statuses os
	ON o.status = os.order_status_id
```
*Ex
```
USE sql_invoicing
;
SELECT p.date, p.invoice_id, p.amount,
	   c.name AS client_name, c.address,
       pm.name AS payment_name
FROM payments p
JOIN clients c
	ON p.client_id = c.client_id
JOIN payment_methods pm
	ON p.payment_method = pm.payment_method_id
```

5. Compound Join Condition
use a combination of values from 2 columns to uniquely identify 1 record
composite primary key (contains more than 1 column)
```
SELECT *
FROM order_items oi
JOIN order_item_notes oin
	ON oi.order_id = oin.order_id
    AND oi.product_id = oin.product_id
```

6. Implicit Join Syntax

better to use Explicit Join Syntax --> use JOIN
( Not recommended because if you forget the WHERE condition, it results in a cross join
  — every row in table1 is combined with every row in table2. )
```
SELECT *
FROM orders o, customers c
WHERE o.customers_id = c.customer_id
```
  =
```
SELECT *
FROM orders o
JOIN customers c 
	ON o.customer_id = c.customer_id
```

7.Outer Joins
```
SELECT 
	c.customer_id, c.first_name,
    o.order_id
FROM customers c
JOIN orders o 
	ON c.customer_id = o.customer_id
ORDER BY c.customer_id
```
can't see the result of the customers who don't have order  
--> use outer Joins (Inner Joins and Outer Joins)  
1) when use LEFTJOIN:
   `LEFT JOIN orders o `
   every record in left table (c, the first) will be returned, whether the condition is true or not
2) when use RIGHTJOIN:
   `RIGHT JOIN orders o`
   every record in right table (o) will be returned, whether the condition is true or not

when use JOIN = INNER JOIN
when use LEFT JOIN = LEFT OUTER JOIN  
		 RIGHT JOIN = RIGHT OUTER JOIN  

*Ex  
```
SELECT 
	p.product_id, p.name, 
    oi.quantity  
FROM products p 
LEFT JOIN order_items oi
	ON p.product_id = oi.product_id
```

   
