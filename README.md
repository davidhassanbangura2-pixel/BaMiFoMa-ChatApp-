# Ba MiFoMa Chat Android

Native Android starter using Kotlin, XML views, and Google Nearby Connections with the `P2P_CLUSTER` strategy.

## Included

- Application ID / namespace: `com.bamifoma.chat`
- Dark theme (`#0B141A`) with Ba MiFoMa green (`#25D366`)
- Eight XML layouts: home chats, chat, registration, OTP, profile setup, settings, chat row, message bubble
- All / Unread / Archived filters, local chat search, demo registration and profile flow
- Offline Chat Mode and Battery Saver settings
- Nearby advertising, discovery, connection acceptance, and text payload sending

## Build a debug APK

Open this folder in Android Studio with JDK 17 and Android SDK Platform 35 installed, allow Gradle sync, then run:

```sh
./gradlew assembleDebug
```

The debug APK is written to `app/build/outputs/apk/debug/app-debug.apk`. If opening from a terminal without a wrapper, install Gradle 8.9 and run `gradle wrapper --gradle-version 8.9` once, then run the command above.

## Important implementation notes

- This workspace did not include a JDK, Gradle, or Android SDK, so no APK was compiled or device-tested here.
- OTP is a local demo (`123456`); real phone verification requires a backend and an SMS/verification provider.
- Chat history and profile setup are currently local/demo UI. The Nearby manager sends text only to connected peers; persistence, identity verification, encryption/key management, delivery receipts, and production safety checks are not implemented.
- Nearby Connections chooses Bluetooth/Wi-Fi transports. The “10 m” and “100 m” indicators are approximate product copy, not guaranteed ranges or separate transport controls. Google Play services availability and Android permissions are required on devices.
- The app targets Android 15 / API 35 with a minimum API 23. APK size depends on Android Gradle Plugin, target ABI, and device packaging; the 8 MB goal needs a real release build and measurement.