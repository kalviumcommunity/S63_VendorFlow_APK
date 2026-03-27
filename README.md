Stateless & Stateful Widgets Demo (Flutter)
Project Overview

This project demonstrates the fundamental concepts of StatelessWidget and StatefulWidget in Flutter by building a simple interactive application.

The app highlights the difference between static and dynamic UI components and shows how Flutter efficiently updates only the required parts of the interface.

Objective
Understand the difference between Stateless and Stateful widgets
Learn when to use each type
Build an interactive UI combining both concepts
Observe UI updates based on user interaction
Concepts Explained
Stateless Widget

A StatelessWidget is immutable, meaning its UI does not change once it is built.

Use Cases:
Static text
Icons
Headers
Layout structures
Example:
class HeaderWidget extends StatelessWidget {
const HeaderWidget({super.key});

@override
Widget build(BuildContext context) {
return const Text(
"Interactive Counter App",
style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
);
}
}

This widget remains unchanged unless rebuilt by its parent.

Stateful Widget

A StatefulWidget can change its state during runtime and rebuild its UI dynamically.

Use Cases:
Counters
Toggles (Dark/Light mode)
Animations
Form inputs
Example:
class CounterWidget extends StatefulWidget {
const CounterWidget({super.key});

@override
State<CounterWidget> createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
int count = 0;

void increment() {
setState(() {
count++;
});
}

@override
Widget build(BuildContext context) {
return Column(
children: [
Text("Count: $count", style: const TextStyle(fontSize: 20)),
ElevatedButton(
onPressed: increment,
child: const Text("Increase"),
),
],
);
}
}

The setState() method triggers a UI rebuild when data changes.

Demo App Structure

File location:
lib/screens/stateless_stateful_demo.dart

Features:
Header (Stateless Widget)
Displays a static title: "Interactive Counter App"
Counter (Stateful Widget)
Button click increases the count
UI updates instantly
UI Interaction Flow
Initial State:
Counter = 0
Static header is displayed
After Interaction:
Button click increases the counter
UI updates dynamically


Testing and Verification
Stateless widget remains unchanged
Stateful widget updates on interaction
UI refresh is efficient and smooth