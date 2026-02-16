---
title:      Building iOS & Android apps with RN Expo
date:       2026-02-16 12:30:00
categories: [mobile]
tags:       [development, mobile, node, typescript, react-native, ios, android]
author:     atomoil

---

Useful package.json scripts for building React Native expo projects for iOS and Android


package.json (snip):

```
  "scripts": {
    "reset": "expo prebuild --clean",
    "ios:release": "expo prebuild && cd ios && pod install && cd .. && xed ios && echo '⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️⬇️\n\nNow run the release build in Xcode\n\n⬆️⬆️⬆️⬆️⬆️⬆️⬆️⬆️⬆️⬆️⬆️⬆️⬆️⬆️'",
    "android:aab": "expo prebuild && cd android && ./gradlew clean && ./gradlew bundleRelease && cd ../ && open android/app/build/outputs/bundle/release",
    "android:apk": "expo prebuild && cd android && ./gradlew assembleRelease"
  }

```
