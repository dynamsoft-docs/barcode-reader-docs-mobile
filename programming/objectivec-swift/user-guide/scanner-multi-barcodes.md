---
layout: default-layout
title: Scan Multiple Barcodes with BarcodeScanner - Dynamsoft Barcode Reader for iOS
description: Use BarcodeScanner iOS edition to scan multiple barcodes
keywords: Multiple barcodes, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Scan multiple barcodes

This article will show you how to configure your barcode scanner to scan multiple barcodes.

## Enable multi-barcode scanning

You can use method `scanningMode` to switch between single-barcode and multi-barcode scanning modes.

- `multiple`: Multi-barcode scanning mode.
- `single`: (Default) Single-barcode scanning mode.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.scanningMode = DSScanningModeMultiple;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.scanningMode = .multiple
```

**Related APIs**

- [`scanningMode`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#scanningmode)

## Configure the auto-stop conditions

There are two automatic stop conditions for multi-code scanning:

- The number of successfully decoded barcodes reaches the `expectedBarcodesCount`.
- There are no new decoding results for N consecutive frames. The value of N can be set using `maxConsecutiveStableFramesToExit`.

For example. Here we apply the following settings:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DSBarcodeScannerConfig *config = [[DSBarcodeScannerConfig alloc] init];
config.expectedBarcodesCount = 10;
config.maxConsecutiveStableFramesToExit = 15;
```
2. 
```swift
let config = BarcodeScannerConfig()
config.expectedBarcodesCount = 10
config.maxConsecutiveStableFramesToExit = 15
```

If there are at least 10 barcodes decoded, it will stop scanning. Otherwise, it will keep scanning for 15 frames. If there are still no barcodes decoded in the 15 frames, it will stop scanning.

**Related APIs**

- [`expectedBarcodesCount`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#expectedbarcodescount)
- [`maxConsecutiveStableFramesToExit`]({{ site.dbr_ios_api }}barcode-scanner/barcode-scanner-config.html#maxconsecutivestableframestoexit)
