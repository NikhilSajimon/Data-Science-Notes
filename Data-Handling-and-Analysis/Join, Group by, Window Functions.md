##  JOINs – Combining Tables

Used to merge datasets, essential for feature engineering and exploratory analysis.

### 1. `INNER JOIN`
```sql
SELECT o.order_id, c.name
FROM orders o
INNER JOIN customers c ON o.customer_id = c.customer_id;
```

### 2. `LEFT JOIN`
```sql
SELECT c.name, o.order_id
FROM customers c
LEFT JOIN orders o ON c.customer_id = o.customer_id;
```

### 3. `RIGHT JOIN`
```sql
SELECT o.order_id, c.name
FROM orders o
RIGHT JOIN customers c ON o.customer_id = c.customer_id;
```

### 4. `FULL OUTER JOIN`
```sql
SELECT c.name, o.order_id
FROM customers c
FULL OUTER JOIN orders o ON c.customer_id = o.customer_id;
```

---

## GROUP BY – Aggregation

Used to summarize data, often for KPIs or feature generation.

### Example: Total orders per customer
```sql
SELECT customer_id, COUNT(*) AS total_orders
FROM orders
GROUP BY customer_id;
```

### Example: Average purchase amount per city
```sql
SELECT city, AVG(purchase_amount) AS avg_spend
FROM customers
GROUP BY city;
```

---

## Window Functions – Advanced Analytics

Window functions allow row-wise calculations across partitions.

### 1. `ROW_NUMBER()`
```sql
SELECT name, salary,
       ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) AS dept_rank
FROM employees;
```

### 2. `RANK()` vs `DENSE_RANK()`
```sql
SELECT name, salary,
       RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;
```

### 3. `LEAD()` and `LAG()` – Time Series Prep
```sql
SELECT date, sales,
       LAG(sales, 1) OVER (ORDER BY date) AS prev_day_sales,
       LEAD(sales, 1) OVER (ORDER BY date) AS next_day_sales
FROM daily_sales;
```

### 4. `NTILE()` – Binning
```sql
SELECT name, salary,
       NTILE(4) OVER (ORDER BY salary) AS salary_quartile
FROM employees;
```

---

##  Aggregate Functions

These are essential for summarizing data.

| Function     | Description                          | Example                              |
|--------------|--------------------------------------|--------------------------------------|
| `COUNT()`    | Number of rows                       | `COUNT(*)`                           |
| `SUM()`      | Total of values                      | `SUM(sales)`                         |
| `AVG()`      | Average value                        | `AVG(age)`                           |
| `MIN()`      | Minimum value                        | `MIN(salary)`                        |
| `MAX()`      | Maximum value                        | `MAX(score)`                         |
| `STDDEV()`   | Standard deviation                   | `STDDEV(sales)`                      |
| `VARIANCE()` | Variance of values                   | `VARIANCE(sales)`                    |

---

##  Data Cleaning with SQL

### 1. Handling NULLs
```sql
SELECT name, COALESCE(age, 0) AS age
FROM customers;
```

### 2. Filtering NULLs
```sql
SELECT * FROM customers
WHERE age IS NOT NULL;
```

### 3. Removing Duplicates
```sql
SELECT DISTINCT name, city
FROM customers;
```

---

##  Useful String Functions

### 1. `LOWER()` / `UPPER()`
```sql
SELECT LOWER(name), UPPER(city) FROM customers;
```

### 2. `SUBSTRING()` / `LEFT()` / `RIGHT()`
```sql
SELECT SUBSTRING(name, 1, 3) AS short_name FROM customers;
```

### 3. `TRIM()` / `LTRIM()` / `RTRIM()`
```sql
SELECT TRIM(name) FROM customers;
```

### 4. `CONCAT()` and `||`
```sql
SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM users;
-- or
SELECT first_name || ' ' || last_name AS full_name FROM users;
```

---

##  Date & Time Functions

### 1. Extracting parts of a date
```sql
SELECT EXTRACT(YEAR FROM order_date) AS year,
       EXTRACT(MONTH FROM order_date) AS month
FROM orders;
```

### 2. Date arithmetic
```sql
SELECT order_date,
       order_date + INTERVAL '7 days' AS delivery_date
FROM orders;
```

---

##  Subqueries & CTEs

### 1. Subquery
```sql
SELECT name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```

### 2. Common Table Expression (CTE)
```sql
WITH high_earners AS (
    SELECT name, salary
    FROM employees
    WHERE salary > 100000
)
SELECT * FROM high_earners;
```

