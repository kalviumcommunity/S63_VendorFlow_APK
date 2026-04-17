
## 📤 Firebase Storage Media Upload (Flutter)

### 📌 Overview

This project demonstrates how to **pick an image from the device, upload it to Firebase Storage, retrieve the download URL, and display it inside the Flutter app**. Firebase Storage provides a secure and scalable solution for handling media files.

---

### ⚙️ Setup

Added dependencies:

```yaml id="7z7cnq"
dependencies:
  firebase_storage: ^12.0.0
  image_picker: ^1.0.0
```

Ran:

```bash id="6m9n0e"
flutter pub get
```

---

### 🖼️ Pick Image from Gallery

```dart id="tvq6lk"
final ImagePicker picker = ImagePicker();

final XFile? file =
    await picker.pickImage(source: ImageSource.gallery);
```

This allows the user to choose an image from the device gallery.

---

### ☁️ Upload Image to Firebase Storage

```dart id="0hcltv"
final fileName =
    DateTime.now().millisecondsSinceEpoch.toString();

await FirebaseStorage.instance
    .ref('uploads/$fileName.jpg')
    .putFile(File(file!.path));
```

The image is uploaded inside the `uploads/` folder in Firebase Storage.

---

### 🔗 Get Download URL

```dart id="bl0l10"
final url = await FirebaseStorage.instance
    .ref('uploads/$fileName.jpg')
    .getDownloadURL();
```

Used to access and display the uploaded image.

---

### 🖥️ Display Uploaded Image

```dart id="l2pk4l"
Image.network(url)
```

Shows the uploaded image instantly in the app UI.

---

### 🚀 Features Implemented

* Pick image from gallery
* Upload image to Firebase Storage
* Retrieve download URL
* Display uploaded image in Flutter UI
* Real-time visual feedback after upload

---

### 🧪 Testing

Verified that:

* Image selected successfully
* Upload completed without errors
* File visible in Firebase Storage Console
* Image displayed correctly in the app

---

### 🪞 Reflection

Firebase Storage is useful for media-heavy apps because it securely stores images, videos, and documents without managing custom servers. My final app can use uploads for profile pictures, product images, documents, or user posts. The main challenge was handling file permissions and path conversion, which was solved using `image_picker`.

