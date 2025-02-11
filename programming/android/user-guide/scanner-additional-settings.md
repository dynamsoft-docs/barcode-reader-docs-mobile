---
layout: default-layout
title: Additional Settings for BarcodeScanner - Dynamsoft Barcode Reader for Android
description: Add additional settings for BarcodeScanner on Android platform. Including auto-zoom, beep, etc.
keywords: BarcodeScanner, scanner, Android, auto-zoom, zoom, beep
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

## Additional Settings for BarcodeScanner

The article will show you how to add additional settings for BarcodeScanner.

### Auto Zoom Feature

Enable the camera to zoom-in automatically when:

- The barcodes are too small.
- The barcodes are farway from the camera.

<div align="center">
    <p><img src="../../assets/auto-zoom.gif" width="30%" alt="auto-zoom"></p>
    <p>Auto Zoom</p>
</div>

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setAutoZoomEnabled(true);
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   isAutoZoomEnabled = true
}
```

**Related API**

- [`setAutoZoomEnabled`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setautozoomenabled)

### Beep

Let the app to trigger a beep sound when a barcode is decoded.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setBeepEnabled(true);
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   isBeepEnabled = true
}
```

**Related API**

- [`setBeepEnabled`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setbeepenabled)
