The SELECT statement & clause

'''
USE sql_store; #(select database)

SELECT *
FROM customers
-- WHERE customers_id=1 (or #WHERE customers_id=1)
ORDER BY first_name
'''

# clause: FROM,WHERE,ORDER BY are optional; cant change the order
;

'''
SELECT
    first_name,
    last_name,
    points,
    (points + 10) * 100 AS 'discount_factor'
FROM customers
'''

# * -> return all columns / specify the column we want to return
#        / use a arithmetic expression / use an alias for a column
;

'''
SELECT DISTINCT state
FROM customers
'''
# remove the duplicates
;

4.HW
'''
SELECT
    name,
    unit_price,
    unit_price * 1.1 AS 'new_price'
FROM products
'''
