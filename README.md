You are required to build a complete CRUD (Create, Read, Update, Delete) workflow in your Flutter application using Firebase Authentication and Cloud Firestore. Your CRUD operations must be fully user-specific — meaning each user can only manage their own data.

Your submission should include:

A Flutter project integrating UI + Firestore + Auth for full CRUD.
A Pull Request (PR) containing all CRUD-related code changes.
A video demonstration uploaded to Google Drive, with edit access enabled for all.
Scenario-Based Task (Must Be Shown in Video Demo)
Your app includes a feature called “My Notes” where each authenticated user can create, view, edit, and delete their personal notes stored in Firestore.

In your video, you must demonstrate:

1. Authentication
Sign in using Firebase Auth (Email/Password or Google).
Show that a user must be authenticated before CRUD actions happen.
2. Create
Add a new note using the UI.

Note gets stored under:

/users/{uid}/items/{itemId}
3. Read
Display a list of notes belonging ONLY to the authenticated user.
Show real-time updates using a StreamBuilder.
4. Update
Edit an existing note and show the change reflecting instantly.
5. Delete
Remove a note and show it disappearing from the list.
6. Firestore Rules Verification
(even brief is enough)

match /users/{uid}/items/{itemId} {
  allow read, write: if request.auth.uid == uid;
}