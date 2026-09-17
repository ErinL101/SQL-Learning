1.`IN`  

```
SELECT *
FROM customers
WHERE state='VA' OR state='GA' OR state='FL'
```
equivalent to `WHERE state IN ( 'VA','FL','GA' )`    
can't be `state = 'VA' OR 'GA' OR 'FL' ` <- we use OR to combine multiple conditions, condition should be a expression but not a string 
can't combine a string with Boolean expression which produce a Boolean value  

*EX  
```
SELECT *
FROM products
WHERE quantity_in_stock IN (49, 38, 72)
```

2.`BETWEEN`  
`WHERE points >= 1000 AND points <= 3000`  
equivalent to  
`WHERE points BETWEEN 1000 AND 3000`  
[1000,3000]  

*EX
```
SELECT *
FROM customers
WHERE birth_date BETWEEN '1990-01-01' AND '2000-01-01'
```

3.`LIKE`  
```
WHERE last_name LIKE 'b%'
```
```
WHERE last_name LIKE '%b%'
```
```
WHERE last_name LIKE 'b____y'
```
`%`: indicate any numbe of characters    
`_`: indicate any a single characters  

  *EX
  ```
SELECT *
FROM customers
WHERE address LIKE '%trail%' OR 
	  address LIKE '%avenue%'
;

SELECT *
FROM customers
WHERE phone NOT LIKE '%9'
```

4.`REGEXP`  



