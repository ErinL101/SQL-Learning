Simplify JOIN clause  
If the column's names are same across 2 tables -- replace ON clause with Using clause

eg:
```
USE sql_store ;
SELECT 
	o.order_id, 
    c.first_name,
    sh.name AS shipper
FROM orders o
JOIN customers c
	-- ON o.customer_id = c.customer_id
    USING (customer_id)
LEFT JOIN shippers sh
	USING (shipper_id)
```

```
SELECT *
FROM order_items oi
JOIN order_item_notes oin
	-- ON oi.order_id = oin.order_id AND oi.product_id = oin.product_id
    USING (order_id, product_id)
```

* Ex
```
USE sql_invoicing;
SELECT p.date,
	   c.name AS client,
       p.amount,
       pm.name 
FROM payments p
LEFT JOIN clients c
	USING (client_id)
LEFT JOIN payment_methods pm
	ON pm.payment_method_id = p.payment_method
```

