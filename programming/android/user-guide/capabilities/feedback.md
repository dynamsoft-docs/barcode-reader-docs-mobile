---
layout: default-layout
title: Add Scan Feedback for BarcodeScanner - Dynamsoft Barcode Reader for Android
description: Learn how to enable scan feedback for BarcodeScanner on Android, including beep and vibration.
keywords: BarcodeScanner, scanner, Android, feedback, beep, vibration
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Add Scan Feedback

Trigger a beep sound or vibration when a barcode is scanned successfully.

### Use BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setBeepEnabled(true);
config.setVibrateEnabled(true);
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   isVibrateEnabled = true
   isBeepEnabled = true
}
```

**Related API**

- [`isVibrateEnabled`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#isvibrateenabled)
- [`isBeepEnabled`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#isbeepenabled)

### Use Foundational APIs

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
Feedback.beep();
Feedback.vibrate();
```
2. 
```kotlin
Feedback.beep()
Feedback.vibrate()
```

**Related API**

- [`Feedback`]({{ site.dce_android }}auxiliary-api/dcefeedback.html)
