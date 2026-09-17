1.`IN`  

```
SELECT *
FROM customers
WHERE state='VA' OR state='GA' OR state='FL'
```
equivalent to `WHERE state IN ( 'VA','FL','GA' )`    
can't be `state = 'VA' OR 'GA' OR 'FL' ` <- we use OR to combine multiple conditions, condition should be a expression but not a string 
can't combine a string with Boolean expression which produce a Boolean value  

