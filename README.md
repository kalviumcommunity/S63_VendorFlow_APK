Firebase Integration in Flutter App
Project Description
This project demonstrates the integration of Firebase Authentication and Cloud Firestore into a Flutter application. It enables user signup/login functionality and real-time data storage with CRUD operations.

The goal is to build a scalable backend system that supports authentication and live data updates for future application features.

Features Implemented
Firebase project setup and configuration

Email & Password Authentication (Signup/Login/Logout)

Firestore database integration

CRUD operations (Create, Read, Update, Delete)

Real-time data display using StreamBuilder

Navigation between authentication screens

Folder Structure
lib/
├── main.dart
├── screens/
│   ├── login_screen.dart
│   ├── signup_screen.dart
│   └── home_screen.dart
├── services/
│   ├── auth_service.dart
│   └── firestore_service.dart
├── widgets/
├── models/
Setup Instructions
1. Firebase Setup
   Create a project in Firebase Console

Add Android/iOS app

Download config files:

google-services.json → android/app/

GoogleService-Info.plist → ios/Runner/

2. Install Dependencies
   Add in pubspec.yaml:

dependencies:
firebase_core: ^3.0.0
firebase_auth: ^5.0.0
cloud_firestore: ^5.0.0
Run:

flutter pub get
3. Configure Firebase
   Run:

flutterfire configure
4. Initialize Firebase
   In main.dart:

import 'package:firebase_core/firebase_core.dart';

void main() async {
WidgetsFlutterBinding.ensureInitialized();
await Firebase.initializeApp();
runApp(MyApp());
}
Authentication Logic
auth_service.dart
import 'package:firebase_auth/firebase_auth.dart';

class AuthService {
final FirebaseAuth _auth = FirebaseAuth.instance;

Future<User?> signUp(String email, String password) async {
try {
final credential = await _auth.createUserWithEmailAndPassword(
email: email,
password: password,
);
return credential.user;
} catch (e) {
print(e);
return null;
}
}

Future<User?> login(String email, String password) async {
try {
final credential = await _auth.signInWithEmailAndPassword(
email: email,
password: password,
);
return credential.user;
} catch (e) {
print(e);
return null;
}
}

Future<void> logout() async {
await _auth.signOut();
}
}
Firestore Logic
firestore_service.dart
import 'package:cloud_firestore/cloud_firestore.dart';

class FirestoreService {
final FirebaseFirestore _db = FirebaseFirestore.instance;

Future<void> addUserData(String uid, Map<String, dynamic> data) async {
await _db.collection('users').doc(uid).set(data);
}

Stream<QuerySnapshot> getData() {
return _db.collection('users').snapshots();
}

Future<void> updateData(String uid, Map<String, dynamic> data) async {
await _db.collection('users').doc(uid).update(data);
}

Future<void> deleteData(String uid) async {
await _db.collection('users').doc(uid).delete();
}
}
UI Screens
Signup Screen
Email and password input

Calls signUp()

Navigates to home screen on success

Login Screen
Email and password input

Calls login()

Redirects to dashboard

Home Screen
Displays Firestore data

Allows add, update, delete operations

Real-Time Data Display
StreamBuilder(
stream: FirestoreService().getData(),
builder: (context, snapshot) {
if (!snapshot.hasData) return CircularProgressIndicator();

    var docs = snapshot.data!.docs;

    return ListView(
      children: docs.map((doc) {
        return ListTile(
          title: Text(doc['name']),
        );
      }).toList(),
    );
},
);