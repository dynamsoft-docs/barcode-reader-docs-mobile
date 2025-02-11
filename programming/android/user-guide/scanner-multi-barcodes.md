---
layout: default-layout
title: Scan Multiple Barcodes with BarcodeScanner - Dynamsoft Barcode Reader for Android
description: Use BarcodeScanner Android edition to scan multiple barcodes
keywords: Multiple barcodes, Android
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Scan multiple barcodes

This article will show you how to configure your barcode scanner to scan multiple barcodes.

## Enable multi-barcode scanning

You can use method `setScanningMode` to switch between single-barcode and multi-barcode scanning modes.

- `SM_MULTIPLE`: Multi-barcode scanning mode.
- `SM_SINGLE`: (Default) Single-barcode scanning mode.

**Code Snippet**

```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setScanningMode(EnumScanningMode.SM_MULTIPLE);
```

## Configure the auto-stop conditions

There are two automatic stop conditions for multi-code scanning:

- The number of successfully decoded barcodes reaches the `expectedBarcodesCount`.
- There are no new decoding results for N consecutive frames. The value of N can be set using `setMaxConsecutiveStableFramesToExit`.

For example. Here we apply the following settings:

```java
BarcodeScannerConfig config = new BarcodeScannerConfig();
config.setScanningMode(EnumScanningMode.SM_MULTIPLE);
config.setExpectedBarcodesCount(10);
config.setMaxConsecutiveStableFramesToExit(15);
```

If there are at least 10 barcodes decoded, it will stop scanning. Otherwise, it will keep scanning for 15 frames. If there are still no barcodes decoded in the 15 frames, it will stop scanning.

**Related APIs**

- [`setScanningMode`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setscanningmode)
- [`setExpectedBarcodesCount`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setexpectedbarcodescount)
- [`setMaxConsecutiveStableFramesToExit`]({{ site.dbr_android_api }}barcode-scanner/barcode-scanner-config.html#setmaxconsecutivestableframestoexit)
