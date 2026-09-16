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
string==texture data = characters --> need to enclose 双引号quote or 单引号
```
SELECT *
FROM customers
WHERE birth_date > '1990-01-01'
```

4.
use quote to present date values
standard format of data 'yyyy-mm-dd'
```
SELECT *
FROM orders
WHERE order_date >= '2019-01-01'
```
