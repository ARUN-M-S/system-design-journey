# 📌 Indexing in Databases

Indexing is a data structure technique used to quickly retrieve records from a database. Indexes are created on columns that are frequently used in `WHERE`, `JOIN`, `ORDER BY`, and `GROUP BY` clauses.

---

## 🚀 Why Use Indexes?

- ⚡ Faster data retrieval
- 📉 Reduces I/O cost
- 🧠 Improves query performance

---

## 🧱 Types of Indexes

### 1. **Single-Column Index**
```sql
CREATE INDEX idx_employee_name ON Employee(Name);

 ```

## 2. Composite Index (Multi-column)
```sql
CREATE INDEX idx_employee_name_dept ON Employee(Name, DepartmentId);
Note: Order matters in composite indexes. (Name, DepartmentId) is not the same as (DepartmentId, Name)
 ```

## 3. Unique Index

```sql
CREATE UNIQUE INDEX idx_unique_email ON Employee(Email); 
```

## 4. Full-Text Index (for search)
```sql
CREATE FULLTEXT INDEX idx_ft_description ON Products(Description);
```
## 📌 When to Use Indexes
✅ Use indexes on:

Columns used in WHERE conditions

JOIN keys

ORDER BY / GROUP BY columns

Foreign keys

## ❌ Avoid indexing:

Columns with low cardinality (e.g., gender: M/F)

Frequently updated columns (index maintenance overhead)

Too many indexes on the same table (can slow down INSERT/UPDATE)

🔍 Example
```sql 
SELECT Name, Salary
FROM Employee
WHERE Department = 'Engineering'
ORDER BY Salary DESC;
Indexing Department and Salary helps improve this query's speed.
```

### 🛠️ Check Existing Indexes

```sql 
SHOW INDEX FROM Employee;
```
## ⚠️ Tips
Use EXPLAIN or EXPLAIN ANALYZE to check if your query uses indexes.

Keep indexes updated with table changes.

Use indexing wisely — more indexes ≠ better always.

