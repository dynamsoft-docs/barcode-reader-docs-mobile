---
layout: default-layout
title: Additional Settings for BarcodeScanner - Dynamsoft Barcode Reader for iOS
description: Add additional settings for BarcodeScanner on iOS platform. Including auto-zoom, beep, etc.
keywords: BarcodeScanner, scanner, iOS, auto-zoom, zoom, beep
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
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isAutoZoomEnabled = true;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isAutoZoomEnabled = true
```

**Related API**

- [`autoZoomEnabled`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#isautozoomenabled)

### Beep

Let the app to trigger a beep sound when a barcode is decoded.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isBeepEnabled = true;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isBeepEnabled = true
```

**Related API**

- [`isBeepEnabled`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#isbeepenabled)
