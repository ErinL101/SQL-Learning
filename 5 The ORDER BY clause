
the default order is by the primary key column
`ORDER BY first_name DESC`

sort data by multiple columns
```
SELECT last_name
FROM customers
ORDER BY state, first_name DESC
```
in MySQL can sort by any columns, whether or not the column is in the SELECT clause

```
SELECT first_name, last_name, 10 AS points
FROM customers
ORDER BY 1,2 
```
(1 means the first column in the SELECT clause)

*EX
```
SELECT *
FROM order_items
WHERE order_id = 2
ORDER BY quantity * unit_price DESC
```
