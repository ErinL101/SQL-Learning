1 NATURAL JOINS 
dataset engine will join based on common columns (columns with the same name)  
```
SELECT *
FROM orders o
NATURAL JOIN customers s
```
easy to code but somewhat dangerous - can produce unexpexted results  


2 Cross Joins
combine every records from the first table and every from second table  

* explicit syntax:
```
SELECT 
  c.first_name AS customer,
  p.name AS product
FROM customers c
CROSS JOIN products p
ORDER BY c.first_name
```

* implicit syntax
```
SELECT 
  c.first_name AS customer,
  p.name AS product
FROM customers c, products p  *
ORDER BY c.first_name
```

*Ex
```
SELECT s.name, p.name
FROM shippers s
CROSS JOIN products p
```
```
SELECT s.name, p.name
FROM shippers s, products p
```

