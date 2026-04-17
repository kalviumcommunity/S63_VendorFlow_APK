# Flutter Complex Form Validation – Profile Details Form

## Project Overview
This Flutter project implements a **multi-field validated form** using `Form`, `TextFormField`, and `GlobalKey<FormState>`.

Feature implemented: **Profile Details Form**

Users must complete all fields correctly before submission.

---

# Validations Included

| Field | Validation Rule |
|------|----------------|
| Full Name | Required + Minimum length |
| Email | Valid email format |
| Phone Number | Exactly 10 digits |
| Password | Minimum 8 characters |
| Confirm Password | Must match password |

---

# Key Flutter Concepts Used

- `Form`
- `TextFormField`
- `GlobalKey<FormState>`
- `validator`
- `TextEditingController`
- `SnackBar`

---

# Main Screen Code

## `profile_form_screen.dart`

```dart id="code001"
import 'package:flutter/material.dart';

class ProfileFormScreen extends StatefulWidget {
  @override
  State<ProfileFormScreen> createState() =>
      _ProfileFormScreenState();
}

class _ProfileFormScreenState
    extends State<ProfileFormScreen> {

  final _formKey = GlobalKey<FormState>();

  final nameController = TextEditingController();
  final emailController = TextEditingController();
  final phoneController = TextEditingController();
  final passwordController = TextEditingController();
  final confirmController = TextEditingController();

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Profile Details Form"),
      ),
      body: Padding(
        padding: EdgeInsets.all(16),
        child: Form(
          key: _formKey,
          child: ListView(
            children: [

              TextFormField(
                controller: nameController,
                decoration:
                    InputDecoration(labelText: "Full Name"),
                validator: (value) {
                  if (value == null || value.isEmpty) {
                    return "Full Name required";
                  }
                  if (value.length < 3) {
                    return "Minimum 3 characters";
                  }
                  return null;
                },
              ),

              SizedBox(height: 12),

              TextFormField(
                controller: emailController,
                decoration:
                    InputDecoration(labelText: "Email"),
                validator: (value) {
                  if (value == null || value.isEmpty) {
                    return "Email required";
                  }

                  if (!RegExp(
                    r'^[^@]+@[^@]+\.[^@]+',
                  ).hasMatch(value)) {
                    return "Enter valid email";
                  }

                  return null;
                },
              ),

              SizedBox(height: 12),

              TextFormField(
                controller: phoneController,
                keyboardType: TextInputType.number,
                decoration:
                    InputDecoration(labelText: "Phone"),
                validator: (value) {
                  if (value == null || value.isEmpty) {
                    return "Phone required";
                  }

                  if (value.length != 10) {
                    return "Phone must be 10 digits";
                  }

                  return null;
                },
              ),

              SizedBox(height: 12),

              TextFormField(
                controller: passwordController,
                obscureText: true,
                decoration:
                    InputDecoration(labelText: "Password"),
                validator: (value) {
                  if (value == null || value.isEmpty) {
                    return "Password required";
                  }

                  if (value.length < 8) {
                    return "Minimum 8 characters";
                  }

                  return null;
                },
              ),

              SizedBox(height: 12),

              TextFormField(
                controller: confirmController,
                obscureText: true,
                decoration: InputDecoration(
                  labelText: "Confirm Password",
                ),
                validator: (value) {
                  if (value !=
                      passwordController.text) {
                    return "Passwords do not match";
                  }
                  return null;
                },
              ),

              SizedBox(height: 25),

              ElevatedButton(
                onPressed: submitForm,
                child: Text("Save Profile"),
              )
            ],
          ),
        ),
      ),
    );
  }

  void submitForm() {
    if (_formKey.currentState!.validate()) {
      ScaffoldMessenger.of(context).showSnackBar(
        SnackBar(
          content:
              Text("Profile Saved Successfully"),
        ),
      );
    }
  }
}