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

# conflict ❓❓
```sql 
SELECT name, purchase_amount 
FROM customers
ORDER BY purchase_amount DESC, name ASC;
```


## ***Group by***

What if you're asked to find the average purchase amount by country? Simply using the AVG() function isn't enough.

This is where the GROUP BY clause comes in handy in SQL. It helps you answer questions like:

- What is the average purchase amount of customers in each country?
- What are the highest and lowest purchase amounts in each country?


```sql
-- Group data by different country

SELECT country, purchase_amount
FROM Customers
GROUP BY country;

country	| purchase_amount
Canada	| 6000
UK	    | 2000
USA	    | 1000
```

>The output shows the country and purchase amount of the first customer in each country, but this isn't a meaningful summary.

>Therefore, the GROUP BY clause is almost always used in conjunction with aggregate functions such as SUM(), MIN(), COUNT(), etc., to summarize data.



### However, when using GROUP BY with aggregate functions, the WHERE clause doesn't work, resulting in an error.


```sql
Write an SQL query to find the total sales for each product that exceeds 1700. The query should return the product name and total sales for each product.

Hint: The total sales of a product is calculated by multiplying the price and quantity for each sale.


SELECT product ,SUM(quantity * price) as total_sales
FROM Sales
GROUP BY product
HAVING SUM(quantity * price)>1700;
```



## SQL CASE


it is similar to if-else / switch case of progrmaming language.

```sql
-- Write your SQL code below
SELECT *,
    CASE
        WHEN country IN('USA','Canada') THEN 'North America'
        WHEN country IN('Sweden','Czech Republic') THEN 'Europe'
        ELSE 'Other'

    END as continent
FROM Customers;
```

```sql
SELECT first_name,country,
    CASE
        WHEN country IN('USA','Canada') THEN 'North America'
        WHEN country IN('Sweden','Czech Republic') THEN 'Europe'
        ELSE 'Other'

    END as continent
FROM Customers
WHERE age < 26;
```

**TEST**  
Questions to Answer  
In this recap, you'll explore the following questions about the company's employees:  

1. High-Earning Employees
Which employees have the highest salaries, listed in descending order?
2. Salary Insights
What is the salary range (highest and lowest) in each department?
3. Workforce Distribution
How many employees are there in each department?
Which departments have fewer than two employees?
4. Targeted Training and Events
Which employees' names contain the letter "J"?
Which employees are eligible for promotion based on their years of service?




🔹 COUNT(*)

- Har row count karta hai
- NULL ho ya na ho → row count hogi
- Safest & standard

🔹 COUNT(column_name)

- Sirf non-NULL values count karta hai
- Agar column mein NULL hua → wo row ignore ho jayegi



Visuallyy
```
Employees
------------------------------------------------
id | name     | department
------------------------------------------------
1  | Peter    | Operations
2  | Meghan   | Sales
3  | Jow      | Tech
4  | Mike     | Sales
5  | Mary     | Operations
7  | Elon     | Tech
8  | Samantha | Marketing
9  | John     | Sales
```

2️⃣ GROUP BY department kya karta hai?  
```
OPERATIONS bucket
-----------------
Peter
Mary


SALES bucket
------------
Meghan
Mike
John


TECH bucket
-----------
Jow
Elon


MARKETING bucket
----------------
Samantha

```

whereas 
```
SELECT department, COUNT(*)
FROM Employees
GROUP BY department;
```

```

department   | count
--------------------
Operations   | 2
Sales        | 3
Tech         | 2
Marketing    | 1

```

```
COUNT(*)        → counts rows
COUNT(column)   → counts NON-NULL values only
```

```sql
Meghan
Mike
John
NULL

--COUNT(*)
Sales → 4

--COUNT(name)
Sales → 3   ❌ (NULL ignore ho gaya)

--Rule
COUNT(*)        → counts rows
COUNT(column)   → counts NON-NULL values only


--GROUP BY pehle rows ko groups mein baantta hai phir aggregation un groups par kaam karti hai


FROM
 ↓
WHERE
 ↓
GROUP BY
 ↓
AGGREGATION (COUNT, SUM, AVG...)
 ↓
SELECT
 ↓
ORDER BY

➡️ Isliye SELECT * + GROUP BY ❌ invalid hota hai

```

```
GROUP BY = bucket banana
COUNT/SUM = bucket ka hisaab

```

