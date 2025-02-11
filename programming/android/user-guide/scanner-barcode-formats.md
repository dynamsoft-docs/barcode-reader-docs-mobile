---
layout: default-layout
title: Specify barcode formats for BarcodeScanner - Dynamsoft Barcode Reader for Android
description: Customize the UI of BarcodeScanner on Android platform.
keywords: BarcodeScanner, scanner, Android, scan region, torch button, close button, scan laser
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Specify Barcode Formats

Set the supported barcode format is always the first step when configuring the BarcodeScanner. You can specify the barcode format via the method `setBarcodeFormats`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setBarcodeFormats(EnumBarcodeFormat.BF_ONED | EnumBarcodeFormat.BF_QR_CODE);
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   barcodeFormats = EnumBarcodeFormat.BF_ONED or EnumBarcodeFormat.BF_QR_CODE
}
```

**Related APIs**

- [`setBarcodeFormats`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setbarcodeformats)
