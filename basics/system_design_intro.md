# 🏗️ Introduction to System Design

## 💡 What is System Design?

System Design is the process of defining the architecture, components, modules, interfaces, and data for a system to satisfy specified requirements.

In simpler terms, it's **how you plan and organize the structure** of your software or product — like the blueprint of a building before it's constructed.

---

## 🧱 Types of Design

### 1. High-Level Design (HLD) - "The Big Picture"
- Focuses on **architecture** of the system.
- Describes **how components interact**, **data flow**, **system boundaries**, etc.
- It answers:
  - How many services are needed?
  - Where to use load balancers, databases, queues, etc.?
  - How will clients interact with servers?

✅ **Example:** You’re designing a social media app. HLD defines components like Web App, Backend API, DB, Caching Layer, etc.

---

### 2. Low-Level Design (LLD) - "The Internal Workings"
- Focuses on **individual components** or classes inside each module.
- Involves **class diagrams**, **methods**, **attributes**, and **object-oriented design**.
- Defines **how exactly** each feature will be implemented.

✅ **Example:** In the "User Service" from HLD, LLD would define the `User` class, its attributes like `id`, `email`, and methods like `createUser()`, `updateUser()`.

---

## 🔍 Why is System Design Important?

1. 🧠 **Scalability:** Helps build systems that can handle millions of users.
2. 💥 **Performance:** Ensures your app is fast and responsive under load.
3. 🔁 **Reliability:** Keeps services available even when things go wrong.
4. 🛠️ **Maintainability:** Easier to update and debug.
5. 🧩 **Team Collaboration:** Everyone understands the architecture and can build independently.

---

## 🎯 Summary

| Aspect              | High-Level Design (HLD)        | Low-Level Design (LLD)            |
|---------------------|-------------------------------|------------------------------------|
| Scope               | Entire system                 | Specific modules/classes           |
| Output              | System architecture, diagrams | Class diagrams, method details     |
| Focus               | How components interact       | How components are implemented     |
| Tools               | Block diagrams, UML           | Class diagrams, sequence diagrams  |

---

## 🔜 What’s Next?

In the following sections, we’ll cover:
- Scalability
- Latency vs Throughput
- Load Balancers, Databases, Caching
- Real-world case studies like Instagram, WhatsApp, etc.

