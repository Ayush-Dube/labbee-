## SQL - structured query language

Unlike known values, you cannot use comparison operators when working with NULL. Instead, use IS NULL or IS NOT NULL.

```sql
SELECT *
FROM Employees
WHERE last_name IS NULL
AND first_name LIKE '%e';
```

###  **Aggregate Functions**

>To derive insights from the data, you need to analyze and summarize this information.  

There are five commonly used aggregate functions:

1. MIN()
2. MAX()
3. COUNT()
4. SUM()
5. AVG()


DISTINCT keyword selects unique rows.

```sql
SELECT COUNT(DISTINCT department)
FROM Employees;
```
>A common mistake is writing SELECT DISTINCT COUNT(department) instead of COUNT(DISTINCT department). Always ensure the DISTINCT keyword is used inside the COUNT() function. 

```sql

--Write an SQL query to select the count of distinct products from the ByteCore or ZapTech brands.

-- Also, the column name in the output should be distinct_product.

SELECT COUNT(DISTINCT name)as distinct_product FROM Products WHERE brand IN('ByteCore','ZapTech');

```

### *SQL SUM() Function*

The SUM() function calculates the total sum of a numeric column.
```sql
-- Return the total of all employees' salaries

SELECT SUM(salary) 
FROM Employees;
```

<!-- SELECT SUM(age)/COUNT(age) from Employees; -->

```sql
--Write an SQL query to calculate the total quantity of products whose price is more than 160.
--Also, the column name in the output should be total_products.

SELECT SUM(quantity) as total_products FROM Products WHERE price > 160;
```




## organize data effectively using SQL
` ORDER BY `

```sql
SELECT * FROM Customers ORDER BY name DESC;
```