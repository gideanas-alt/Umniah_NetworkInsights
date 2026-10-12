# Handset Build and Installation Guide

This package is the Android source SDK/project for **Umniah Network Insights**.

> Important: Android handsets install an **APK** (or an App Bundle through Google Play), not an SDK ZIP. This source package must be compiled in Android Studio before it can be installed on a phone.

## Required workstation tools

- Android Studio compatible with Android Gradle Plugin 9.4
- JDK 17
- Android SDK Platform 37
- Android SDK Build Tools 36.0.0 or newer compatible build tools
- Gradle 9.6 (AGP 9.4 minimum)

## Build a debug APK

1. Extract this ZIP to a local folder.
2. Open the extracted root folder in Android Studio.
3. Let Android Studio install missing SDK components and sync the Gradle project.
4. Select the `app` configuration.
5. Build **Build > Build APK(s)**, or run `:app:assembleDebug` from the Gradle tool window.
6. The debug APK will be generated under:

   `app/build/outputs/apk/debug/app-debug.apk`

The debug application ID is:

`com.umniah.networkinsights.debug`

## Install on a physical Android phone

### Option A - Android Studio

1. Enable Developer options and USB debugging on the phone.
2. Connect the phone by USB.
3. Approve the USB-debugging prompt on the phone.
4. Select the phone from Android Studio's device selector.
5. Press **Run**.

### Option B - Install the APK manually

1. Transfer `app-debug.apk` to the phone.
2. Open the APK on the phone.
3. Allow installation from that file source if Android asks.
4. Install the app.

### Option C - ADB

`adb install -r app/build/outputs/apk/debug/app-debug.apk`

## Runtime permissions

The application intentionally requests permissions only when the related feature is used. Detailed cell/radio information can require location permission on Android because Android protects CellInfo behind location access. Subscription information can require phone-state permission. Precise and background location remain optional and should not be enabled without explicit user consent and an approved privacy policy.

## Safe test defaults

- Production telemetry upload is disabled until a real governed Umniah API endpoint and authentication flow are configured.
- The app does not collect IMEI, IMSI, ICCID, SMS, contacts, call recordings, passwords, or unrelated application content.
- Missing or restricted telecom measurements remain unavailable; they are not fabricated.
- Throughput tests remain policy-gated until an approved operator measurement endpoint is configured.

## Production signing

The debug APK is for handset testing only. For production distribution, create an Umniah-controlled Android signing key, configure a release signing profile outside source control, build a signed release AAB/APK, and complete the Android/Google Play privacy and permission declarations.
