Smart Street Vendor App (Flutter)
Project Description
This project is the initial setup for a Flutter-based mobile application aimed at improving street-food ordering systems. The goal is to build a scalable app that will later support features like digital menus, order management, and real-time updates using Firebase.

This phase focuses on setting up the Flutter environment, understanding project structure, and building a basic interactive UI.

Folder Structure
lib/
├── main.dart        # Entry point of the application
├── screens/         # Contains different UI screens (e.g., WelcomeScreen)
├── widgets/         # Reusable UI components (buttons, cards, etc.)
├── models/          # Data models (used later for structured data)
├── services/        # Backend logic (Firebase/API integration in future)
Explanation
main.dart
The starting point of the app. It initializes the app and defines the root widget.

screens/
Contains full UI pages. Each screen represents a separate view in the app (e.g., Home, Menu, Orders).

widgets/
Stores reusable components to avoid code duplication and improve maintainability.

models/
Defines data structures for the app, such as order, user, or menu item (used in later stages).

services/
Handles backend logic like Firebase authentication, database access, and APIs.

Naming Conventions
File names: lowercase with underscores
Example: welcome_screen.dart

Class names: PascalCase
Example: WelcomeScreen

Variables and functions: camelCase
Example: toggleText()

Widgets: Named based on purpose
Example: CustomButton, MenuCard

Setup Instructions
1. Install Flutter
   Download and install Flutter SDK from the official website

Add Flutter to system PATH

2. Install IDE
   Install Android Studio or VS Code

Add Flutter and Dart extensions

3. Verify Installation
   Run the following command:

flutter doctor
Fix any issues shown in the output.

4. Create Project
   flutter create your_project_name
   cd your_project_name
5. Run the App
   flutter run
   Make sure:

Emulator or physical device is connected

Default Flutter Demo App runs successfully

UI Implementation
The default counter app is replaced with a custom Welcome Screen that includes:

Scaffold with AppBar

Column layout

Text widget (title)

Image/Icon

Button (ElevatedButton)

State change on button click (toggle text/color)

This demonstrates:

Widget composition

State management using StatefulWidget

Basic Dart syntax