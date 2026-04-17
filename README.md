

## 🔍 Firestore Querying, Filtering & Sorting (Flutter)

### 📌 Overview

This project demonstrates how to **retrieve only required data from Cloud Firestore** using queries such as `where()`, `orderBy()`, and `limit()`. This improves performance, reduces unnecessary reads, and creates a cleaner user experience.

---

### ⚙️ Setup

Added dependency:

```yaml id="jlwmzq"
dependencies:
  cloud_firestore: ^5.0.0
```

Firebase initialized successfully in the app.

---

### 🔎 Query Features Used

#### ✅ Filter with `where()`

```dart id="e6r9b7"
.where('isCompleted', isEqualTo: false)
```

Shows only pending tasks.

#### ✅ Sort with `orderBy()`

```dart id="0n2j7r"
.orderBy('priority')
```

Displays tasks in ascending priority order.

#### ✅ Limit Results

```dart id="e59j8u"
.limit(10)
```

Loads only the first 10 documents for faster performance.

---

### 🖥️ StreamBuilder UI Example

```dart id="nhjlwm"
StreamBuilder(
  stream: FirebaseFirestore.instance
      .collection('tasks')
      .where('isCompleted', isEqualTo: false)
      .orderBy('priority')
      .limit(10)
      .snapshots(),
  builder: (context, snapshot) {
    if (!snapshot.hasData) {
      return Center(child: CircularProgressIndicator());
    }

    final docs = snapshot.data!.docs;

    return ListView.builder(
      itemCount: docs.length,
      itemBuilder: (context, index) {
        final task = docs[index];

        return ListTile(
          title: Text(task['title']),
          subtitle: Text('Priority: ${task['priority']}'),
        );
      },
    );
  },
);
```

---

### 🚀 Features Implemented

* Filtered pending tasks only
* Sorted tasks by priority
* Limited results for better speed
* Real-time UI updates using Firestore streams

---

### 🧪 Testing

Using Firebase Console:

* Added new tasks → appeared instantly
* Changed priority → reordered automatically
* Completed task → removed from filtered list

---

### 🪞 Reflection

Querying improves performance because the app fetches only necessary data instead of loading full collections. I selected filters based on real use cases such as pending tasks and priority sorting. The main challenge was Firestore index creation, which was solved using the generated console link.

---

