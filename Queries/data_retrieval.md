-- 1. Total spent by customer
``` BEGIN
   DBMS_OUTPUT.PUT_LINE(
     ecommerce_pkg.get_total_spent(1)
   );
END;
/
```

-- customerid,productid,productQty For placing order
```
SET SERVEROUTPUT ON
BEGIN
  place_order(5, 4, 15);
END;
/
```

Customer who spent more than Average
```
SELECT customerid, fullname
FROM customer
WHERE customerid IN (
    SELECT customerid
    FROM orders
    GROUP BY customerid
    HAVING SUM(totalamount) >
        (SELECT AVG(totalamount) FROM orders)
);



```
Update Product Price using Package
```
BEGIN
ecommerce_pkg.update_product_price(12,200);
END;
```

Testing Trigger
```
update product set price = 200 where productid = 9;
```

--Total sales per product
```
SELECT
    p.productid,
    p.name,
    SUM(oi.quantity) AS total_units_sold,
    SUM(oi.subtotal) AS total_sales
FROM product p
JOIN orderitem oi ON p.productid = oi.productid
GROUP BY p.productid, p.name;
```
Placing order via Procedure
```
SET SERVEROUTPUT ON
BEGIN
  place_order(5, 4, 15);
END;
/
```

Check Stock Status
```
DECLARE
    v_status VARCHAR2(50);
BEGIN
    v_status := check_stock_status(3);
    DBMS_OUTPUT.PUT_LINE('Stock status = ' || v_status);
END;
/
```








