---
layout: default-layout
title: Configure Barcode Scanner - Dynamsoft Barcode Reader Android Edition
description: Configure the barcode scan settings via BarcodeScannerConfig class when using Barcode Scanner Android Edition
keywords: Configure, config, BarcodeScannerConfig, Android
breadcrumbText: Configure Barcode Scanner
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Configure the barcode scan settings

When developing with [`BarcodeScannerActivity`](../api-reference/barcode-scanner/barcode-scanner-activity.md), you can add configurations via the [`BarcodeScannerConfig`](../api-reference/barcode-scanner/barcode-scanner-config.md) class. This page will guide you on how to configure the settings.

## Barcode Decode Settings

### Set the barcode format via APIs

Set the supported barcode format is always the first step when creating a barcode scanner. It improves the processing speed and the accuracy.

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

### Setup a customized template file

A template file is a JSON file that includes a series of algorithm parameter settings. It is always used to customize the performance for different usage scenarios. [Contact us](https://www.dynamsoft.com/company/customer-service/#contact) to get a customized template for your scanner.

1. Add a **Templates** folder to the assets folder of your project at **src\main\assets\Templates**. Put your JSON file in the **Templates** folder. Here we use a **ReadQRCode.json** file as an example.

    <div align="left">
    <p><img src="../../assets/init-settings-from-file-android.png" alt="initSettings" width="50%" /></p>
    </div>

2. Specify the template file via setTemplateFilePath

<div class="sample-code-prefix"></div>
>- Java
>- Kotlin
>
>1. 
```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setTemplateFilePath("ReadQRCodes.json");
```
2. 
```kotlin
val config = BarcodeScannerConfig().apply {
   templateFilePath = "ReadQRCodes.json"
}
```

**Related APIs**

- [`setBarcodeFormats`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setbarcodeformats)
- [`setTemplateFilePath`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#settemplatefilepath)

## Configure the UI Elements

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

## Additional Settings

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

## Further Customization

If you have other customization requirements on the `BarcodeScanner` component, you can modify it with the [open source code on GitHub](https://github.com/Dynamsoft/barcode-reader-mobile/).
