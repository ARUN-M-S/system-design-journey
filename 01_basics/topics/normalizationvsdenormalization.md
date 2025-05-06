# 🧠 Normalization vs Denormalization

This document compares **Normalization** and **Denormalization** — two core concepts in data modeling and system design. Understanding the trade-offs between them is crucial for building scalable, maintainable, and performant systems.

---

## 📌 What is Normalization?

**Normalization** is the process of organizing data to reduce redundancy and improve data integrity by dividing large tables into smaller, related tables.

### 🔍 Key Goals:
- Eliminate data redundancy
- Maintain data integrity
- Improve consistency
- Optimize write operations

### ✅ Benefits:
- Avoids data anomalies (insert, update, delete)
- Saves storage space
- Clear relationships using foreign keys

### ⚠️ Trade-offs:
- Requires complex joins for queries
- Slightly slower reads in read-heavy systems

---

## 📌 What is Denormalization?

**Denormalization** is the process of combining related tables into one to optimize read performance, often by introducing redundancy.

### 🔍 Key Goals:
- Improve query performance (especially reads)
- Reduce joins and simplify data access
- Optimize for specific access patterns

### ✅ Benefits:
- Faster read operations
- Better performance for reporting and analytics
- Reduced need for joins

### ⚠️ Trade-offs:
- Increased data redundancy
- Higher risk of data inconsistency
- More complex write logic (e.g., updates to multiple places)

---

## 🔄 Normalization vs Denormalization: Quick Comparison

| Feature                  | Normalization                         | Denormalization                        |
|--------------------------|----------------------------------------|----------------------------------------|
| **Redundancy**           | Low (removes redundancy)              | High (adds redundancy)                 |
| **Data Integrity**       | High                                   | Lower (risk of inconsistency)          |
| **Read Performance**     | Moderate to Low (needs joins)         | High (less joins)                      |
| **Write Performance**    | High (fewer fields to update)         | Lower (duplicate updates needed)       |
| **Storage Usage**        | Efficient                              | Higher                                 |
| **Use Case**             | OLTP (transactional systems)          | OLAP, reporting, caching, NoSQL models |

---

## 🧪 Real-World Example

### Scenario: E-commerce Order

#### Normalized Model:
- `users` table
- `orders` table with `user_id`
- `order_items` table with `order_id`, `product_id`

#### Denormalized Model:
- `orders` table with embedded user and items data (JSON or flat fields)

---

## 🧠 When to Normalize

- OLTP systems (e.g., banking, inventory)
- Systems needing strong consistency
- Write-heavy applications
- Small to medium scale with complex relationships

## 🚀 When to Denormalize

- OLAP systems (analytics, dashboards)
- Read-heavy systems (e.g., news feed)
- Cache layers or NoSQL databases
- Systems with fixed or known query patterns

---

## 📌 Conclusion

Both normalization and denormalization have their place in system design. Choose **normalization** when you need data integrity and optimized writes. Choose **denormalization** when performance and read efficiency outweigh storage concerns.

👉 **Design for your use case, not just best practices.**
