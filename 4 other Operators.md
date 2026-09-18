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
4.1
REGEXP = Regular Expression
powerful for searching strings  

```
WHERE last_name REGEXP 'field'
```
equivalent to `WHERE last_name LIKE '%field%'`

4.2
`^`: present the beginning of the a string
`$`: present the end of a string
`|`: present logical OR (multiple search patterns)  
`[]`:match any characters list in brackets
`[x-x]`:present a range

`WHERE last_name REGEXP '^field'` end with field  
`WHERE last_name REGEXP 'field$|mac|rose'`
`WHERE  last_name REGEXP '[gi]e'` before the letter 'e' either have a 'g' or a 'i'
`WHERE  last_name REGEXP 'e[a-h]'` supply a range of characters-have any characters from a to h after 'e' 

*Ex
! use | to replace or
```
SELECT *
FROM customers
WHERE first_name REGEXP 'ELKA|AMBUR'
;
SELECT *
FROM customers
WHERE last_name REGEXP 'EY$|ON$'
;
SELECT *
FROM customers
WHERE last_name REGEXP '^MY|SE'
;
SELECT *
FROM customers
WHERE last_name REGEXP 'B[RU]'
```




