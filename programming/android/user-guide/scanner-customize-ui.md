---
layout: default-layout
title: Customize the UI of BarcodeScanner - Dynamsoft Barcode Reader for Android
description: Customize the UI of BarcodeScanner on Android platform.
keywords: BarcodeScanner, scanner, Android, scan region, torch button, close button, scan laser
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Configure the UI Elements

BarcodeScanner provides a set of UI elements that can be easily customized.

<div align="center">
    <p><img src="../../assets/barcode-scanner-ui.png" width="70%" alt="barcode-scanner"></p>
    <p>Barcode Scanner UI Components</p>
</div>

- Close button: Stop barcode scanning and go back to the previous activity.
- Scan Region: Set a region of interest so that the algorithm focus on this region only. It can sharpenly improve the processing speed. For some special barcode types like DotCode the scan region improves the read-rate as well.
- Torch button: A clickable button that can turn on/off the torch.
- Scan Laser: A line that moving up and down. Its moving area is limited in the scan region.

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
// Margin left 15%, margin top 30%, margin right 85%, margin bottom 70%
config.setScanRegion(new DSRect(0.15f, 0.25f, 0.85f, 0.65f, true));
config.setTorchButtonVisible(true);
config.setCloseButtonVisible(true);
config.setScanLaserVisible(true);
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   // Margin left 15%, margin top 30%, margin right 85%, margin bottom 70%
   scanRegion = DSRect(0.15f, 0.3f, 0.85f, 0.7f, true)
   torchButtonVisible = true
   closeButtonVisible = true
   scanLaserVisible = true
}
```

**Related APIs**

- [`setScanRegion`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setscanregion)
- [`setTorchButtonVisible`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#settorchbuttonvisible)
- [`setScanLaserVisible`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setscanlaservisible)
- [`setCloseButtonVisible`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setclosebuttonvisible)
