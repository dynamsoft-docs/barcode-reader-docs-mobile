---
layout: default-layout
title: Customize the UI of BarcodeScanner - Dynamsoft Barcode Reader iOS
description: Learn how to customize the BarcodeScanner UI on iOS.
keywords: BarcodeScanner, scanner, iOS, scan region, torch button, close button, scan laser
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Configure the UI Elements

| Available Buttons |
| ----------------- |
| Torch button |
| Camera toggle button |
| Close button (BarcodeScanner API only) |

BarcodeScanner provides a set of UI elements that you can easily customize.

<div align="center">
    <p><img src="../../../assets/buttons.png" width="70%" alt="barcode-scanner"></p>
    <p>Barcode Scanner UI Components</p>
</div>

- Torch button: A clickable button that turns the torch on or off.
- Camera toggle button: A clickable button that switches the front/back-facing camera.
- Close button: Stops barcode scanning and returns to the previous activity.

## Work with Foundational APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, strong) DSCameraView *cameraView;
self.cameraView = [[DSCameraView alloc] initWithFrame:self.view.bounds];
[self.cameraView setTorchButtonVisible:YES];
self.cameraView.cameraToggleButtonVisible = YES;
```
2. 
```swift
let cameraView = self.cameraView
cameraView?.torchButtonVisible = true
cameraView?.cameraToggleButtonVisible = true
```

**Related APIs**

- [`CameraView`]({{ site.dce_ios }}auxiliary-api/dcecameraview.html)
  - [setTorchButtonVisible]({{ site.dce_ios }}auxiliary-api/dcecameraview.html#settorchbuttonvisible)
  - [setCameraToggleButtonVisible]({{ site.dce_ios }}auxiliary-api/dcecameraview.html#setcameratogglebuttonvisible)

## Work with BarcodeScanner APIs

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isTorchButtonVisible = YES;
config.isCloseButtonVisible = YES;
config.isCameraToggleButtonVisible = YES;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isTorchButtonVisible = true
config.isCloseButtonVisible = true
config.isCameraToggleButtonVisible = true
```

**Related APIs**

- [`BarcodeScannerConfig`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html)
  - [setTorchButtonVisible]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#settorchbuttonvisible)
  - [setCloseButtonVisible]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#setclosebuttonvisible)
  - [setCameraToggleButtonVisible]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#setcameratogglebuttonvisible)
