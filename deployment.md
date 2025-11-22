# Android Deployment Guide

This guide explains how to build the ** QT Coach** Android app using Capacitor.

## Prerequisites
1.  **Node.js**: Install from [nodejs.org](https://nodejs.org/).
2.  **Android Studio**: Install from [developer.android.com](https://developer.android.com/studio).
    - Ensure the Android SDK and Virtual Device are installed.

## Setup Steps

1.  **Install Dependencies**
    Open a terminal in the project folder (`e:\AIWORK\QTcoach`) and run:
    ```bash
    npm install
    ```

2.  **Initialize Android Project**
    Add the Android platform:
    ```bash
    npx cap add android
    ```

3.  **Sync Web Assets**
    Whenever you modify `index.html`, run this to update the Android project:
    ```bash
    npx cap sync
    ```

4.  **Open in Android Studio**
    ```bash
    npx cap open android
    ```
    - This will launch Android Studio.
    - Wait for Gradle sync to complete.

## Building & Running

-   **Run on Emulator**: Click the **Run** (Play) button in Android Studio.
-   **Build APK**:
    1.  Go to **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
    2.  The APK will be generated in `android/app/build/outputs/apk/debug/`.

## Key Features
-   **Auto-Update**: The app loads `index.html` directly.
-   **Data Sync**: It fetches the latest QT schedule from GitHub (`https://raw.githubusercontent.com/copaland/edu-test/main/qt/qtYYYYmm.csv`).
-   **Sharing**: Uses native Android sharing for KakaoTalk/SMS.

## Troubleshooting
-   **WebView Errors**: If the app shows a white screen, check `Logcat` in Android Studio.
-   **Network Issues**: Ensure the device has internet access to fetch the CSV and Gemini API.
