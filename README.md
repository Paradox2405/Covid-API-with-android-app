# Covid API with Android App

The Android client for a COVID-19 check-in system. Users log in against a PHP web API, then scan a venue's QR code to check in for contact tracing.

## Features

- Login against a REST endpoint (`webApi/Server/User.php`)
- QR code scanning with the camera (`code-scanner`)
- The logged-in user is stored in app settings
- Network debugging with Stetho

## Tech stack

- **Java**, Android SDK (AndroidX, Material Components)
- [Fast Android Networking](https://github.com/amitshekhariitbhu/Fast-Android-Networking) with Jackson for API calls
- `com.budiyev.android:code-scanner` for QR scanning

## Project structure

```
app/src/main/java/com/thils/webApiApp/
  App.java            application class (networking and Stetho setup)
  LoginActivity.java  login screen
  QrScan.java         QR check-in
  model/User.java
  util/Settings.java  saved user and settings
```

## Getting started

1. Run the PHP API locally (for example with XAMPP), so that `http://<host>/webApi/Server/User.php` responds.
2. The app calls `http://10.0.2.2/...`, which is the host machine as seen from the Android emulator. Change the URL in `LoginActivity.java` and `QrScan.java` for a real device.
3. Open the project in Android Studio and run it.

> The default branch of this repo is `Android-app`.
