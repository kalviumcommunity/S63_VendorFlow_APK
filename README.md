Responsive Flutter UI Layout
Project Description
This project demonstrates how to build a responsive user interface in Flutter that adapts to different screen sizes and orientations. The layout dynamically adjusts for mobile and tablet devices using MediaQuery and adaptive widgets.

The goal is to ensure consistent design, proper spacing, and usability across portrait and landscape modes.

Features Implemented
Responsive layout using MediaQuery

Adaptive UI for phone and tablet screens

Portrait and landscape support

Flexible widgets for scalable design

Clean separation of UI components

Folder Structure
lib/
├── main.dart
├── screens/
│   └── responsive_home.dart   # Responsive UI screen
├── widgets/
├── models/
├── services/
Key Concepts Used
1. MediaQuery for Responsiveness
   double screenWidth = MediaQuery.of(context).size.width;
   double screenHeight = MediaQuery.of(context).size.height;

bool isTablet = screenWidth > 600;
Detects device size

Helps switch between layouts

2. Conditional Layout Rendering
   return isTablet
   ? Row(
   children: [
   Expanded(child: leftPanel),
   Expanded(child: rightPanel),
   ],
   )
   : Column(
   children: [
   leftPanel,
   rightPanel,
   ],
   );
   Single-column layout for phones

Two-column layout for tablets

3. Flexible & Adaptive Widgets
   Used the following widgets to ensure responsiveness:

Expanded – distributes space evenly

Flexible – allows flexible sizing

FittedBox – scales child widgets

AspectRatio – maintains consistent proportions

Wrap / GridView – responsive item arrangement

UI Structure
Header Section
AppBar or top container for title/navigation

Main Content Area
Dynamic layout (Column or Row based on screen size)

Footer Section
Button or navigation controls

