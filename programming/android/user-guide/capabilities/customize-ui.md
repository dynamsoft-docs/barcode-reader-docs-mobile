---
layout: default-layout
title: Customize the UI of BarcodeScanner - Dynamsoft Barcode Reader for Android
description: Learn how to customize the BarcodeScanner UI on Android.
keywords: BarcodeScanner, scanner, Android, scan region, torch button, close button, scan laser
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Configure the UI Elements

| Available UI Elements |
| ------------------- |
| Scan region |
| Scan Laser |
| Torch button |
| Camera toggle button |
| Close button (BarcodeScanner API only) |

BarcodeScanner provides a set of UI elements that you can easily customize.

<div align="center">
    <p><img src="../../assets/barcode-scanner-ui.png" width="70%" alt="barcode-scanner"></p>
    <p>Barcode Scanner UI Components</p>
</div>

- Close button: Stops barcode scanning and returns to the previous activity.
- Scan region: Sets a region of interest so the algorithm focuses only on that area. This can significantly improve processing speed. For special barcode types such as DotCode, the scan region can also improve the read rate.
- Scan laser: A line that moves up and down. Its movement is limited to the scan region.
- Torch button: A clickable button that turns the torch on or off.

## Scan Region & Scan Laser

### Configure with BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
// Margin left 15%, margin top 30%, margin right 85%, margin bottom 70%
config.setScanRegion(new DSRect(0.15f, 0.25f, 0.85f, 0.65f, true));
config.setScanLaserVisible(true);
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   // Margin left 15%, margin top 30%, margin right 85%, margin bottom 70%
   scanRegion = DSRect(0.15f, 0.3f, 0.85f, 0.7f, true)
   scanLaserVisible = true
}
```

**Related APIs**

- [`BarcodeScannerConfig`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html)
  - [`setScanRegion`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setscanregion)
  - [`setScanLaserVisible`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setscanlaservisible)

### Configure with Foundational APIs

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CameraView cameraView = findViewById(R.id.camera_view);
CameraEnhancer mCamera = new CameraEnhancer(cameraView, this);
try {
    mCamera.setScanRegion(new DSRect(0.15f, 0.25f, 0.85f, 0.65f, true));
} catch (CameraEnhancerException e) {
    throw new RuntimeException(e);
}
cameraView.setScanLaserVisible(true);
```
2. 
```kotlin
val cameraView = findViewById<CameraView>(R.id.camera_view)
val mCamera = CameraEnhancer(this)
mCamera.scanRegion = DSRect(0.15f, 0.25f, 0.85f, 0.65f, true)
cameraView.isScanLaserVisible = true
```

**Related APIs**

- [`CameraEnhancer`]({{ site.dbr_android_api }}camera-enhancer/camera-enhancer.html)
  - [`setScanRegion`]({{ site.dbr_android_api }}camera-enhancer/camera-enhancer.html#setscanregion)
- [`CameraView`]({{ site.dce_android }}auxiliary-api/dcecameraview.html)
  - [`setScanLaserVisible`]({{ site.dce_android }}auxiliary-api/dcecameraview.html#setscanlaservisible)

## Buttons

### Add Buttons with BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setTorchButtonVisible(true);
config.setCloseButtonVisible(true);
config.setCameraToggleButtonVisible(true);
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   torchButtonVisible = true
   closeButtonVisible = true
   cameraToggleButtonVisible = true
}
```

**Related APIs**

- [`BarcodeScannerConfig`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html)
  - [setTorchButtonVisible]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#settorchbuttonvisible)
  - [setCloseButtonVisible]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setclosebuttonvisible)
  - [setCameraToggleButtonVisible]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setcameratogglebuttonvisible)

### Add Buttons with Foundational APIs

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
CameraView cameraView = findViewById(R.id.camera_view);
cameraView.setTorchButtonVisible(true);
cameraView.setCameraToggleButtonVisible(true);
```
2. 
```kotlin
val cameraView = findViewById<CameraView>(R.id.camera_view)
cameraView.torchButtonVisible = true
cameraView.cameraToggleButtonVisible = true
```

**Related APIs**

- [`CameraView`]({{ site.dce_android }}auxiliary-api/dcecameraview.html)
  - [setTorchButtonVisible]({{ site.dce_android }}auxiliary-api/dcecameraview.html#settorchbuttonvisible)
  - [setCameraToggleButtonVisible]({{ site.dce_android }}auxiliary-api/dcecameraview.html#setcameratogglebuttonvisible)
