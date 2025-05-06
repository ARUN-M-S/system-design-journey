# 🔁 Database Replication

**Database Replication** is the process of copying and maintaining database objects, like tables or entire databases, in multiple database servers. It ensures **data availability**, **redundancy**, and **fault tolerance** across systems.

---

## 📌 Why Replication?

Replication is widely used in distributed systems and high-availability setups to:
- Improve **read scalability**
- Increase **fault tolerance**
- Provide **disaster recovery**
- Enable **geographical distribution**

---

## 🧩 Types of Replication

### 1. 🧠 **Master-Slave (Primary-Secondary)**
- **Master** handles all writes.
- **Slaves** replicate data and handle reads.
- Common in OLTP systems to balance load.

### 2. 🔁 **Master-Master**
- All nodes can read/write.
- Requires conflict resolution.
- Useful for active-active setups (e.g., multi-region apps).

### 3. ⏱️ **Synchronous Replication**
- Data is written to all replicas at the same time.
- Ensures strong consistency.
- Slower, can affect write performance.

### 4. 🔄 **Asynchronous Replication**
- Writes are committed to the primary first, then sent to replicas.
- Fast, but may result in **eventual consistency**.

---

## 🔄 Replication vs Backup

| Feature            | Replication                        | Backup                               |
|--------------------|------------------------------------|--------------------------------------|
| **Purpose**         | High availability & scalability     | Disaster recovery                    |
| **Real-time**       | Yes                                | No (scheduled)                       |
| **Consistency**     | Can be strong or eventual          | Point-in-time                        |
| **Data Access**     | Readable replicas                  | Not directly accessible              |

---

## 💡 Use Cases

- **Read-heavy systems** (e.g., news websites)
- **Disaster recovery setups**
- **Global applications** with regional replicas
- **Data warehousing and analytics**

---

## ⚠️ Challenges

- **Data consistency** (especially with async replication)
- **Conflict resolution** in multi-master setups
- **Latency**
