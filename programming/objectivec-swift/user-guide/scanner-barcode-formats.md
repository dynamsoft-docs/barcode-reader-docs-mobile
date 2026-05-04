---
layout: default-layout
title: Specify Barcode Formats for BarcodeScanner - Dynamsoft Barcode Reader for iOS
description: "Learn how to use Dynamsoft Barcode Reader iOS features with practical setup guidance, workflow tips, and examples for building reliable capture apps today."
keywords: BarcodeScanner, scanner, iOS, barcode formats
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Specify Barcode Formats

Set the supported barcode format is always the first step when configuring the BarcodeScanner. You can specify the barcode format via the method `barcodeFormats`.

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
