---
layout: default-layout
title: Zoom Control for BarcodeScanner - Dynamsoft Barcode Reader iOS
description: Learn how to configure zoom control for BarcodeScanner on iOS, including auto-zoom and zoom factor.
keywords: BarcodeScanner, scanner, iOS, auto-zoom, zoom
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Zoom Control

Zoom control is commonly used when processing small barcodes or scanning from a long distance. There are two zoom control features:

- Auto-zoom: Lets the library determine whether to zoom in.
- Zoom factor: Lets you set the zoom factor directly. This is commonly used when focusing on small barcodes.

## Auto Zoom

Enable auto-zoom so the camera can zoom in automatically.

<div align="center">
    <p><img src="../../../assets/auto-zoom.gif" width="30%" alt="auto-zoom"></p>
    <p>Auto Zoom</p>
</div>

### Use Foundational APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[self.dce enableEnhancedFeatures:DSEnhancedFeaturesAutoZoom];
```
2. 
```swift
dce.enableEnhancedFeatures(EnhancedFeatures.autoZoom)
```

**Related API**

- [`enableEnhancedFeatures`]({{ site.dce_ios }}primary-api/camera-enhancer.html#enableenhancedfeatures)

### Use BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isAutoZoomEnabled = YES;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isAutoZoomEnabled = true
```

**Related API**

- [`setAutoZoomEnabled`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#setautozoomenabled)

## Zoom Factor

### Use Foundational APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[self.dce setZoomFactor:2.0];
```
2. 
```swift
dce.setZoomFactor(2.0)
```

**Related API**

- [`setZoomFactor`]({{ site.dce_ios }}primary-api/camera-enhancer.html#setzoomfactor)

### Use BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.zoomFactor = 2.0;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.zoomFactor = 2.0
```

**Related API**

- [`setZoomFactor`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#setzoomfactor)
