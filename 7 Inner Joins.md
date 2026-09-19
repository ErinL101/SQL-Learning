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
