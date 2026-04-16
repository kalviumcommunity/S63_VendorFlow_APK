Here’s a **clean, small, ready-to-copy README** for your Firestore schema task 👇

---

## 📊 Firestore Database Schema Design

### 📌 Overview

This project defines a scalable and well-structured **Cloud Firestore database schema** for a Flutter application. The goal is to organize data efficiently using collections, documents, and subcollections to support real-time updates and future scalability.

---

### 🧠 Data Requirements

The app manages the following entities:

* Users
* Tasks
* Activity Logs

---

### 🗂️ Firestore Schema Structure

```
users
 └── userId
       ├── name: string
       ├── email: string
       ├── createdAt: timestamp
       └── tasks (subcollection)
             └── taskId
                   ├── title: string
                   ├── description: string
                   ├── isCompleted: boolean
                   ├── createdAt: timestamp

logs
 └── logId
       ├── userId: string
       ├── action: string
       ├── timestamp: timestamp
```

---

### 📄 Sample Documents

**User Document**

```json
{
  "name": "Rahul",
  "email": "rahul@example.com",
  "createdAt": "2026-04-16T10:00:00Z"
}
```

**Task Document**

```json
{
  "title": "Complete Assignment",
  "description": "Finish Flutter project",
  "isCompleted": false,
  "createdAt": "2026-04-16T11:00:00Z"
}
```

**Log Document**

```json
{
  "userId": "user123",
  "action": "Created Task",
  "timestamp": "2026-04-16T11:05:00Z"
}
```

---

### 🧩 Design Decisions

* Used **subcollections (`tasks`)** to handle large, user-specific data efficiently
* Kept documents **flat and simple** to reduce read costs
* Added timestamps for tracking and sorting
* Separated logs into a different collection for better scalability

---

### 📈 Scalability Considerations

* Supports thousands of users with isolated data
* Avoids large arrays by using subcollections
* Optimized for minimal reads and efficient queries

---

### 🪞 Reflection

Designing the schema helped in understanding how to structure NoSQL data efficiently. The main challenge was deciding when to use subcollections vs top-level collections. This structure ensures clarity, scalability, and easy maintenance for future development.

---
