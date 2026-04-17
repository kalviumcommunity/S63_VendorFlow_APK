# Firebase Authentication + Firestore Security Rules (Flutter)

## Project Overview
This Flutter project integrates **Firebase Authentication** and **Cloud Firestore** with **Security Rules** to protect user data.

Feature implemented: **Secure Profile**

Each authenticated user can:

- Sign up / Login
- Create their own profile
- Read their own profile
- Update their own profile

Security enforced:

- Users cannot access another user’s profile
- Unauthorized users cannot read/write data

---

# Firebase Packages Used

```yaml
dependencies:
  firebase_core: ^3.0.0
  firebase_auth: ^5.0.0
  cloud_firestore: ^5.0.0