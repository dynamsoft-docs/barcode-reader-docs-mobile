---
layout: default-layout
title: Specify Barcode Formats for BarcodeScanner - Dynamsoft Barcode Reader for iOS
description: Customize the UI of BarcodeScanner on iOS platform.
keywords: BarcodeScanner, scanner, iOS, barcode formats
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Specify Barcode Formats

Set the supported barcode format is always the first step when configuring the BarcodeScanner. You can specify the barcode format via the method `setBarcodeFormats`.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.barcodeFormats = DSBarcodeFormatOneD | DSBarcodeFormatQRCode;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.barcodeFormats = [.oneD, .qrCode]
```

**Related APIs**

- [`barcodeFormats`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#barcodeformats)
