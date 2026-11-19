# Firebase-Appcheck-Sketchware
Appcheck for firebase 

Firebase App Check + Play Integrity for Sketchware Pro

Project Description

This project demonstrates how to integrate Firebase App Check with Play Integrity into an Android application built using Sketchware Pro.

Firebase App Check helps protect your Firebase resources by verifying the authenticity and integrity of requests coming from your application. It adds an extra layer of security to Firebase services and helps reduce unauthorized access from unofficial clients, modified applications and automated scripts.

This project is designed to help Sketchware Pro developers understand how Firebase App Check works and how to configure it with their own Firebase projects.

Features

- Firebase App Check integration.
- Debug App Check support for development.
- Play Integrity support for production.
- Automatic production App Check token generation.
- App Check success and failure handling.
- Firebase Authentication compatibility.
- Firebase Realtime Database compatibility.

Important: You must configure your own Firebase project before using this project. Do not use another developer's Firebase configuration.

Project link 🖇️ 👇 
https://web.sketchub.in/p/33987

---

1. Requirements

Before starting, make sure you have:

- Sketchware Bro app-release-17e5acd.apk
- Download link 🖇️ 👇 👇
- https://chat.whatsapp.com/KXpL6cWbqFrGBGizs9OmMy?s=cl&p=a&iam=2
- 
- A Firebase account.
- A registered Android application in Firebase.
- Your application's correct package name.
- Your own signing keystore.
- Your release certificate's SHA-256 fingerprint.

---

2. Create Your Own Firebase Project

1. Open "Firebase Console" (https://console.firebase.google.com/).
2. Create a new Firebase project or open an existing one.
3. Go to Project settings.
4. Under Your apps, select Add app.
5. Choose Android.
6. Enter your application's package name.

Important: The package name registered in Firebase must match your Sketchware project package name.

For example:

"com.example.myapp"

7. Register the app.
8. Download your own "google-services.json".

Do not use another developer's Firebase configuration file.

---

3. Configure strings.xml

When changing to your own Firebase project, you need to update the Firebase project configuration in your resources.

In Sketchware Pro:

1. Open your project.
2. Go to Resources Editor.
3. Open "strings.xml".

Here are the important resource names:

String key| Value to obtain
"gcm_defaultSenderId"| "project_info.project_number"

Example

Suppose your Firebase project number is:

"123456789012"

Create the following string:

String key:

"gcm_defaultSenderId"

String value:

"123456789012"

Get the project number from your own Firebase project's "google-services.json".

Important: If the string already exists, edit its value instead of creating a duplicate.

---

4. Configure Firebase App Check

1. Open Firebase Console.
2. Navigate to App Check.
3. Select your registered Android application.
4. Select Play Integrity as your provider.
5. Configure the Play Integrity settings.
6. Make sure the Play Integrity API is enabled in the associated Google Cloud project.

Important settings for APKs distributed outside Google Play

If your application will be distributed through your website or another platform outside Google Play:

- PLAY_RECOGNIZED: Not required (uncheck Play recognition if the console shows it as a requirement).
- LICENSED: Not required.
- Minimum device integrity: Device integrity.

Keep the Play Integrity provider enabled. Do not confuse the Play Integrity provider with the Play recognition verdict.

These settings allow your application to support installations outside Google Play while still requiring device integrity verification.

---

5. Register Your Own SHA-256 Fingerprint

Your signing certificate must be configured correctly.

1. Obtain the SHA-256 fingerprint of your own release keystore.
2. Open Firebase Console.
3. Go to Project settings.
4. Select your Android application.
5. Add your SHA-256 fingerprint.

Important: Use the fingerprint belonging to the certificate that signs your release APK.

If you change your signing certificate later, update the Firebase configuration accordingly.

---

6. Enable App Check Enforcement

After configuring App Check and confirming that your application can obtain valid production tokens:

1. Open Firebase Console.
2. Navigate to App Check.
3. Select Realtime Database.
4. Review your application's verification metrics.
5. Enable enforcement when you are confident that legitimate requests are passing verification.

Repeat the process for other supported Firebase services you use.

Important: Do not enable enforcement blindly. Requests from applications that cannot provide valid App Check tokens may be rejected.

---

7. Important Security Notes

Firebase App Check is not a replacement for Firebase Authentication or Firebase Security Rules.

For proper security, use all three:

- App Check: Helps verify app authenticity.
- Firebase Authentication: Identifies the user.
- Firebase Security Rules: Determines what each user can read or modify.

Never rely on App Check alone to protect sensitive database operations.

For payments, coin deductions, tournament joining, prize distribution and administrative actions, use a trusted backend with proper authorization and validation.

---

Final Notes

Every developer must configure their own:

- Firebase project.
- Firebase configuration.
- Android package name.
- Signing keystore.
- SHA-256 fingerprint.

Never share your private keystore, keystore password, service account private keys or other sensitive credentials.

This project is intended to help Sketchware Pro developers understand and implement Firebase App Check using Play Integrity.

Enjoy building!

Credits: SoftDeveloper
