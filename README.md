

# 🧩 Reusable Widgets in Flutter

## 📌 Project Overview

This project demonstrates how to create **custom reusable widgets** in Flutter to improve code modularity, reduce duplication, and maintain consistent UI design.

A custom `InfoCard` widget is created and reused across multiple screens, along with an optional interactive `LikeButton`.

---

## 🏗️ Custom Widget Implementation

### 🔹 InfoCard (Stateless Widget)

```dart
class InfoCard extends StatelessWidget {
  final String title;
  final String subtitle;
  final IconData icon;

  const InfoCard({
    required this.title,
    required this.subtitle,
    required this.icon,
  });

  @override
  Widget build(BuildContext context) {
    return Card(
      margin: EdgeInsets.all(12),
      child: ListTile(
        leading: Icon(icon),
        title: Text(title),
        subtitle: Text(subtitle),
      ),
    );
  }
}
```

---

## 🔹 Usage in Screens

```dart
InfoCard(
  title: 'Profile',
  subtitle: 'View details',
  icon: Icons.person,
)
```

👉 Reused in multiple screens like Home and Details

---

## 🔹 Optional Stateful Widget (Like Button)

```dart
class LikeButton extends StatefulWidget {
  @override
  _LikeButtonState createState() => _LikeButtonState();
}

class _LikeButtonState extends State<LikeButton> {
  bool _isLiked = false;

  @override
  Widget build(BuildContext context) {
    return IconButton(
      icon: Icon(
        _isLiked ? Icons.favorite : Icons.favorite_border,
      ),
      onPressed: () {
        setState(() {
          _isLiked = !_isLiked;
        });
      },
    );
  }
}
```

---

## 📸 Screenshots (Add)

* Widget used in Home Screen
* Widget used in Details Screen
* Consistent UI across screens

---

## 🧠 Reflection

### 🔹 How do reusable widgets help?

* Reduce code duplication
* Improve readability
* Ensure consistent design

---

### 🔹 Why is modularity important?

* Makes code scalable
* Easier for teams to collaborate
* Simplifies maintenance

---

### 🔹 Challenges faced

* Structuring widget properties
* Passing dynamic data correctly

---

## 🚀 Final Takeaway

> Reusable widgets make Flutter apps cleaner, scalable, and easier to maintain by following a modular design approach.

---
