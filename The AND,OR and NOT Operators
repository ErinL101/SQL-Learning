combine multiple search conditions when filtering data


1.order of operators
AND (first)
OR 
can use parentheses to change orders
```
SELECT *
FROM customers
WHERE
    birth_date > '1990-01-01' OR 
    points > 1000 AND state = 'VA'
```
born either after 1990 or ( have more than 1000 point AND live in VA )


2.NOT
negate the condiotions
```
SELECT *
FROM customers
WHERE NOT ( birth_date > '1990-01-01' OR points > 1000  )
```
equivalent to ` WHERE   birth_date <= '1990-01-01' AND points <= 1000 `

