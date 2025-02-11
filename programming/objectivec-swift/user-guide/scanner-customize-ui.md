---
layout: default-layout
title: Customize the UI of BarcodeScanner - Dynamsoft Barcode Reader for iOS
description: Customize the UI of BarcodeScanner on iOS platform.
keywords: BarcodeScanner, scanner, iOS, scan region, torch button, close button, scan laser
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
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.isCloseButtonVisible = false;
DSRect *region = [[DSRect alloc] init];
region.left = 0.15;
region.top = 0.3;
region.right = 0.85;
region.bottom = 0.7;
config.scanRegion = region;
config.isTorchButtonVisible = false;
config.isScanLaserVisible = false;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.isCloseButtonVisible = false
let region = Rect()
region.left = 0.15
region.top = 0.3
region.right = 0.85
region.bottom = 0.7
config.scanRegion = region
config.isTorchButtonVisible = false
config.isScanLaserVisible = false
```

**Related APIs**

- [`scanRegion`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#scanregion)
- [`isTorchButtonVisible`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#istorchbuttonvisible)
- [`isScanLaserVisible`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#isscanlaservisible)
- [`isCloseButtonVisible`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#isclosebuttonvisible)
