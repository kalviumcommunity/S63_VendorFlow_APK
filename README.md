

# 📱 Responsive Design in Flutter (MediaQuery & LayoutBuilder)

## 📌 Project Overview

This project demonstrates how to build **adaptive and responsive layouts** in Flutter using:

* `MediaQuery` → for dynamic sizing
* `LayoutBuilder` → for conditional layout changes

The app adjusts automatically across different screen sizes (mobile & tablet), ensuring a smooth and consistent user experience.

---

## 🏗️ Implementation

### 🔹 Using MediaQuery (Dynamic Sizing)

```dart id="r1"
var screenWidth = MediaQuery.of(context).size.width;

Container(
  width: screenWidth * 0.8,
  height: 100,
  color: Colors.teal,
  child: Center(child: Text('Responsive Box')),
)
```

👉 Adapts size based on screen width

---

### 🔹 Using LayoutBuilder (Adaptive Layout)

```dart id="r2"
LayoutBuilder(
  builder: (context, constraints) {
    if (constraints.maxWidth < 600) {
      return Column(
        children: [Text('Mobile Layout')],
      );
    } else {
      return Row(
        children: [Text('Tablet Layout')],
      );
    }
  },
)
```

👉 Switches layout based on screen size

---

## 📸 Screenshots (Add)

* Mobile view (Column layout)
* Tablet view (Row layout)

---

## 🧠 Reflection

### 🔹 How do these tools help?

* `MediaQuery` → adjusts size proportionally
* `LayoutBuilder` → changes layout structure

---

### 🔹 Why is responsive design important?

* Supports multiple devices 📱💻
* Prevents UI breaking
* Improves user experience

---

### 🔹 Challenges faced

* Handling layout shifts between screen sizes
* Avoiding overflow issues

---

## 🚀 Final Takeaway

> Using MediaQuery and LayoutBuilder allows Flutter apps to scale and adapt seamlessly across different devices, creating flexible and professional UI designs.

---
