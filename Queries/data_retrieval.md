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
