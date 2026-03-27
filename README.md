Understanding Widget Tree and Reactive UI in Flutter
Project Description
This project demonstrates the core concepts of Flutter’s widget tree and reactive UI model. A simple interactive app is built to show how widgets are structured hierarchically and how the UI updates automatically when the state changes.

What is a Widget Tree?
In Flutter, everything is a widget. The UI is built as a tree of widgets, where each widget is a node in the hierarchy.

The root is usually MaterialApp

It contains child widgets like Scaffold

These further contain layout and UI elements such as Column, Text, and Button

Example Widget Tree Structure
MaterialApp
└── Scaffold
├── AppBar
│     └── Text
└── Body
└── Center
└── Column
├── Text
├── Image/Icon
└── ElevatedButton
This structure shows the parent-child relationship between widgets.

Reactive UI in Flutter
Flutter follows a reactive programming model, meaning:

The UI automatically updates when the data (state) changes

You do not manually redraw the UI

Instead, Flutter rebuilds only the affected widgets

Example Using setState()
int count = 0;

void increment() {
setState(() {
count++;
});
}
When setState() is called:

The state changes

Flutter rebuilds only the necessary part of the widget tree

UI updates instantly

Demo App Overview
A simple app was created with:

A title text

A button

A dynamic value (counter or text)

Features
Displays initial UI state

Button interaction updates UI

Demonstrates real-time state change

Widget Tree for Demo App
Scaffold
├── AppBar
│     └── Text (App Title)
└── Body
└── Center
└── Column
├── Text (Dynamic Content)
└── ElevatedButton (onPressed)
State Change Demonstration
Initial State:
Text shows default value (e.g., "Count: 0")

After Button Click:
Text updates (e.g., "Count: 1")

This shows how Flutter reacts to state changes.