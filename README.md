

# 🚀 Multi-Screen Navigation in Flutter Using Navigator & Named Routes

## 📌 Project Overview

This project demonstrates how to implement **multi-screen navigation** in a Flutter application using the `Navigator` class and **named routes**.

The app includes:

* 🏠 Home Screen
* 📄 Details Screen

Users can navigate smoothly between screens, showcasing a **scalable navigation structure** suitable for real-world applications like dashboards, login flows, and multi-step processes.

---

# 🧠 Understanding Navigation in Flutter

Flutter uses a **stack-based navigation system** managed by the `Navigator`.

### 🔹 Core Concept

> Each new screen is pushed onto a stack, and when navigating back, the top screen is popped off.

---

## 🔄 Navigation Methods Used

| Method                  | Purpose                                   |
| ----------------------- | ----------------------------------------- |
| `Navigator.pushNamed()` | Navigate to a new screen using route name |
| `Navigator.pop()`       | Return to previous screen                 |

---

# 🏗️ Project Structure

```plaintext
lib/
 ├── main.dart
 └── screens/
      ├── home_screen.dart
      └── details_screen.dart
```

---

# 🏠 Home Screen Implementation

```dart
import 'package:flutter/material.dart';

class HomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Home Screen')),
      body: Center(
        child: ElevatedButton(
          onPressed: () {
            Navigator.pushNamed(context, '/details');
          },
          child: Text('Go to Details'),
        ),
      ),
    );
  }
}
```

---

# 📄 Details Screen Implementation

```dart
import 'package:flutter/material.dart';

class DetailsScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final message =
        ModalRoute.of(context)!.settings.arguments as String?;

    return Scaffold(
      appBar: AppBar(title: Text('Details Screen')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(message ?? 'No data received'),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                Navigator.pop(context);
              },
              child: Text('Back to Home'),
            ),
          ],
        ),
      ),
    );
  }
}
```

---

# ⚙️ Route Configuration (`main.dart`)

```dart
import 'package:flutter/material.dart';
import 'screens/home_screen.dart';
import 'screens/details_screen.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      initialRoute: '/',
      routes: {
        '/': (context) => HomeScreen(),
        '/details': (context) => DetailsScreen(),
      },
    );
  }
}
```

---

# 🔄 Passing Data Between Screens

### 🔹 Sending Data

```dart
Navigator.pushNamed(
  context,
  '/details',
  arguments: 'Hello from Home!',
);
```

---

### 🔹 Receiving Data

```dart
final message =
    ModalRoute.of(context)!.settings.arguments as String?;
```

---

# 📸 Screenshots (Add in README)

Include the following:

* ✅ Home Screen
* ✅ Details Screen
* ✅ Navigation transition (before → after button click)

---

# 🎥 Navigation Flow

1. App starts → Home Screen loads
2. User clicks “Go to Details”
3. App navigates to Details Screen
4. User clicks “Back to Home”
5. App returns to Home Screen

👉 Navigation is smooth and responsive using Flutter’s built-in routing system.

---

# 🧠 Reflection

## 🔹 What is the role of the Navigator in Flutter?

The `Navigator` is responsible for managing the **navigation stack of screens** in a Flutter app.

* It controls how screens are added (`push`)
* And how they are removed (`pop`)

👉 This allows smooth transitions and proper back navigation behavior.

---

## 🔹 Why are named routes preferred for larger apps?

Named routes provide:

### ✅ Better Organization

* Centralized route definitions in one place

### ✅ Cleaner Code

* Simplifies navigation calls

```dart
Navigator.pushNamed(context, '/details');
```

### ✅ Scalability

* Easy to add and manage multiple screens

### ✅ Decoupling

* Screens don’t directly depend on each other

---

## 🔹 How does Flutter manage the navigation stack?

Flutter uses a **Last-In-First-Out (LIFO) stack system**:

* New screens are **pushed** onto the stack
* When navigating back, screens are **popped off**

### 💡 Example Flow

```
HomeScreen → push → DetailsScreen
DetailsScreen → pop → HomeScreen
```

👉 This ensures:

* Efficient memory usage
* Smooth user experience

---

# 🚀 Final Takeaway

> Flutter’s Navigator and named routes provide a structured and scalable approach to managing multi-screen navigation, ensuring smooth transitions, clean code architecture, and an intuitive user experience.

---

