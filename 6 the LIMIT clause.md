LIMIT clause should always come at the end

order:
`SELECT`  
`FROM`  
`WHERE`  
`ORDER BY`  
`LIMIT`  


```
SELECT *
FROM customers
LIMIT 300 
```
show the first 3 records

`LIMIT 6,3`  
6 = offset value -> skip the first 6 records then show 3 records

*Ex
```
SELECT *
FROM customers
ORDER BY points DESC
LIMIT 3
```
