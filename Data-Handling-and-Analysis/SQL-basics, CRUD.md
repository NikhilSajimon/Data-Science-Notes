

## What is SQL?

**SQL (Structured Query Language)** is the backbone of data retrieval and manipulation in relational databases. In data science, SQL is used to:
- Extract and filter data for analysis
- Join datasets from multiple tables
- Aggregate and summarize data
- Perform feature engineering
- Prepare data for machine learning models

---

## CRUD Operations

CRUD = **Create, Read, Update, Delete** — the foundation of interacting with any database.

### 1. `INSERT` – Add new data
```sql
INSERT INTO customers (customer_id, name, age, city)
VALUES (101, 'Ravi', 28, 'Mumbai');
```

### 2. `SELECT` – Retrieve data
```sql
SELECT name, age FROM customers
WHERE city = 'Mumbai';
```

### 3. `UPDATE` – Modify existing data
```sql
UPDATE customers
SET age = 29
WHERE customer_id = 101;
```

### 4. `DELETE` – Remove data
```sql
DELETE FROM customers
WHERE customer_id = 101;
```

---

