

# 🎬 Animations in Flutter (Implicit & Explicit)

## 📌 Project Overview

This project demonstrates how to create **smooth and engaging UI animations** in Flutter using:

* Implicit animations (`AnimatedContainer`, `AnimatedOpacity`)
* Explicit animations (`AnimationController`, `RotationTransition`)
* Custom page transitions

The goal is to enhance user experience with fluid and meaningful animations.

---

## 🏗️ Implementation

### 🔹 Implicit Animation (AnimatedContainer)

```dart id="an1"
AnimatedContainer(
  width: _toggled ? 200 : 100,
  height: _toggled ? 100 : 200,
  color: _toggled ? Colors.teal : Colors.orange,
  duration: Duration(seconds: 1),
  child: Center(child: Text('Tap Me')),
)
```

👉 Smoothly animates size and color changes

---

### 🔹 Fade Animation (AnimatedOpacity)

```dart id="an2"
AnimatedOpacity(
  opacity: _toggled ? 1.0 : 0.3,
  duration: Duration(seconds: 1),
  child: Image.asset('assets/images/logo.png'),
)
```

👉 Creates fade-in/fade-out effect

---

### 🔹 Explicit Animation (Rotation)

```dart id="an3"
RotationTransition(
  turns: _controller,
  child: Image.asset('assets/images/logo.png'),
)
```

👉 Provides full control using AnimationController

---

### 🔹 Page Transition Animation

```dart id="an4"
Navigator.push(
  context,
  PageRouteBuilder(
    pageBuilder: (_, __, ___) => NextPage(),
    transitionsBuilder: (_, animation, __, child) {
      return SlideTransition(
        position: Tween(
          begin: Offset(1, 0),
          end: Offset.zero,
        ).animate(animation),
        child: child,
      );
    },
  ),
);
```

👉 Smooth slide transition between screens

---

## 📸 Screenshots / GIFs (Add)

* Animated container (before & after)
* Fade animation
* Rotation animation
* Page transition

---

## 🧠 Reflection

### 🔹 How do animations improve UX?

* Provide visual feedback
* Make interactions feel natural
* Enhance overall app polish

---

### 🔹 Implicit vs Explicit Animations

* Implicit → Simple, automatic transitions
* Explicit → Full control for complex animations

---

### 🔹 Best Practices

* Keep animations smooth and fast (300–800ms)
* Use natural curves (`easeInOut`)
* Avoid overusing animations

---

## 🚀 Final Takeaway

> Animations in Flutter make apps feel alive by turning static UI into smooth, interactive experiences.

---
