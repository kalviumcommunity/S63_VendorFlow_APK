# QuickTabs Navigation

A Flutter app demonstrating tab-based navigation using `BottomNavigationBar` with 3 screens: Home, Explore, and Profile. It uses `IndexedStack` to preserve screen state while switching tabs.

## Features

- BottomNavigationBar with 3 tabs
- Active tab highlight updates correctly
- Smooth instant switching between screens
- Screen state preserved using IndexedStack
- Separate UI for each tab

## Main Code

```dart
int _currentIndex = 0;

final List<Widget> _pages = [
  HomeScreen(),
  ExploreScreen(),
  ProfileScreen(),
];

Scaffold(
  body: IndexedStack(
    index: _currentIndex,
    children: _pages,
  ),
  bottomNavigationBar: BottomNavigationBar(
    currentIndex: _currentIndex,
    onTap: (index) {
      setState(() {
        _currentIndex = index;
      });
    },
    items: const [
      BottomNavigationBarItem(
        icon: Icon(Icons.home),
        label: "Home",
      ),
      BottomNavigationBarItem(
        icon: Icon(Icons.explore),
        label: "Explore",
      ),
      BottomNavigationBarItem(
        icon: Icon(Icons.person),
        label: "Profile",
      ),
    ],
  ),
);