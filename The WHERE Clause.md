1.
WHERE : fliter data

```
USE sql_store
;

SELECT *
FROM customers
WHERE points > 3000
```

2.comparison operators
> / >= / < / <= / = / != / <> (not equal)
```
SELECT *
FROM customers
WHERE state != 'VA'
```

3.
string --> need to enclosed quotes
```
SELECT *
FROM customers
WHERE birth_date > '1990-01-01'
```
 4.
use quotes to present date values
standard date format:  'yyyy-mm-dd'

5.Ex
```
SELECT *
FROM orders
WHERE order_date >= '2019-01-01'
```


