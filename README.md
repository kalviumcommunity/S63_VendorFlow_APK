Flutter Environment Setup and First App Run
Project Description
This project documents the complete setup of the Flutter development environment and the successful execution of a basic Flutter application. It ensures that the system is properly configured for building and testing cross-platform mobile applications.

Steps Followed
1. Install Flutter SDK
   Downloaded Flutter SDK from the official website

Extracted it to a preferred directory

Added flutter/bin to system PATH

Verified installation using:

flutter doctor
2. Set Up Development Environment
   Android Studio
   Installed Android Studio

Installed required components:

Android SDK

Android SDK Platform

Android Virtual Device (AVD) Manager

Installed Flutter and Dart plugins

(Alternative) VS Code
Installed Flutter and Dart extensions

3. Configure Emulator
   Opened AVD Manager in Android Studio

Created a virtual device (e.g., Pixel 6)

Selected system image (Android 13+)

Launched emulator

Verified device detection:

flutter devices
4. Create and Run First Flutter App
   Created project:

flutter create first_flutter_app
cd first_flutter_app
Ran the app:

flutter run
Observed:

Default Flutter counter app displayed on emulator

App successfully builds and runs
