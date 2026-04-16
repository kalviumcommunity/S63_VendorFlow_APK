
---

# 🎨 Responsive Layout in Flutter Using Row, Column & Container

## 📌 Project Overview

This project demonstrates how to build a **responsive and flexible UI layout** in Flutter using core layout widgets:

* `Container` → for structure and styling
* `Row` → for horizontal alignment
* `Column` → for vertical stacking

The layout adapts seamlessly across different screen sizes using `MediaQuery` and `Expanded`, ensuring a consistent user experience on both mobile and tablet devices.

---

# 🧠 Understanding Core Layout Widgets

## 🔹 Container

A `Container` is used to structure UI elements with:

* Padding & margin
* Background color
* Width & height control

```dart id="c1"
Container(
  padding: EdgeInsets.all(16),
  color: Colors.blueAccent,
  child: Text('Hello, Flutter!'),
)
```

---

## 🔹 Row (Horizontal Layout)

```dart id="c2"
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Icon(Icons.home),
    Icon(Icons.search),
    Icon(Icons.person),
  ],
)
```

👉 Used for horizontal alignment of elements

---

## 🔹 Column (Vertical Layout)

```dart id="c3"
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
    Text('Welcome!'),
    SizedBox(height: 10),
    ElevatedButton(onPressed: () {}, child: Text('Click Me')),
  ],
)
```

👉 Used for stacking elements vertically

---

# 🏗️ Layout Implementation

## 📱 Screen: `responsive_layout.dart`

This layout includes:

* Header section
* Two panels (left & right)
* Responsive structure

---

## 💡 Full Implementation

```dart id="c4"
import 'package:flutter/material.dart';

class ResponsiveLayout extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    double screenWidth = MediaQuery.of(context).size.width;

    bool isTablet = screenWidth > 600;

    return Scaffold(
      appBar: AppBar(title: Text('Responsive Layout')),
      body: Container(
        padding: EdgeInsets.all(16),
        child: Column(
          children: [
            // Header
            Container(
              width: double.infinity,
              height: 150,
              color: Colors.lightBlueAccent,
              child: Center(child: Text('Header Section')),
            ),
            SizedBox(height: 10),

            // Responsive Body
            Expanded(
              child: isTablet
                  ? Row(
                      children: [
                        Expanded(
                          child: Container(
                            color: Colors.amber,
                            child: Center(child: Text('Left Panel')),
                          ),
                        ),
                        SizedBox(width: 10),
                        Expanded(
                          child: Container(
                            color: Colors.greenAccent,
                            child: Center(child: Text('Right Panel')),
                          ),
                        ),
                      ],
                    )
                  : Column(
                      children: [
                        Expanded(
                          child: Container(
                            color: Colors.amber,
                            child: Center(child: Text('Top Panel')),
                          ),
                        ),
                        SizedBox(height: 10),
                        Expanded(
                          child: Container(
                            color: Colors.greenAccent,
                            child: Center(child: Text('Bottom Panel')),
                          ),
                        ),
                      ],
                    ),
            ),
          ],
        ),
      ),
    );
  }
}
```

---

# 📱 Responsiveness Strategy

## 🔹 Using `MediaQuery`

```dart id="c5"
double screenWidth = MediaQuery.of(context).size.width;
bool isTablet = screenWidth > 600;
```

👉 Detects screen size dynamically

---

## 🔹 Adaptive Layout Behavior

| Screen Size   | Layout              |
| ------------- | ------------------- |
| Small devices | Vertical (`Column`) |
| Large devices | Horizontal (`Row`)  |

---

## 🔹 Using `Expanded`

* Ensures equal space distribution
* Prevents overflow issues
* Maintains layout balance

---

# 📸 Screenshots (Add in README)

Include:

* ✅ Mobile View (Vertical layout)
* ✅ Tablet View (Horizontal layout)
* ✅ Landscape mode

---

# 🧠 Reflection

## 🔹 Why is responsive design important?

Responsive design ensures that the app:

* Works across multiple devices 📱💻
* Maintains usability and readability
* Provides a consistent user experience

👉 Without responsiveness:

* UI may break ❌
* Content may overflow ❌

---

## 🔹 Challenges Faced

* Handling layout switching between devices
* Avoiding overflow in smaller screens
* Maintaining consistent spacing

### 💡 Solution

* Used `MediaQuery` for dynamic decisions
* Used `Expanded` to distribute space properly
* Avoided fixed widths/heights

---

## 🔹 How do MediaQuery and Expanded help?

### ✅ MediaQuery

* Detects screen size
* Enables adaptive layouts

### ✅ Expanded

* Distributes available space evenly
* Prevents layout breaking

---

# 🚀 Final Takeaway

> By combining `Row`, `Column`, and `Container` with responsive techniques like `MediaQuery` and `Expanded`, we can build flexible Flutter layouts that adapt smoothly across different devices and screen sizes.

---


