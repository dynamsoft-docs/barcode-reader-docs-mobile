---
layout: default-layout
title: Dynamsoft Barcode Reader Flutter API Reference - BarcodeScanner API Main Page
description: This is the main page of the BarcodeScanner (Ready-To-Use) API for Flutter.
keywords: api reference, Flutter, barcode reader, ready to use, 
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
---

# BarcodeScanner (Ready-To-Use) API Reference

As mentioned in the Introduction page, the Barcode Reader can be implemented either via a set of *Ready-To-Use API* or the *Capture Vision Foundational API*. Each has its own draws and benefits, so even though the Ready-To-Use Edition is sufficient for most cases, it is careful to consider which edition your usage scenario requires.

The BarcodeScanner class is built on top of the Capture Vision Foundational API to offer a faster and smoother development experience, providing a more sophisticated UI while not sacrificing any performance aspect of the library.

> [!NOTE]
> In order to use the BarcodeScanner class, you must include *dynamsoft_barcode_reader_bundle_flutter* in the project dependencies.
> Please note that *dynamsoft_barcode_reader_bundle_flutter* is dependent on *dynamsoft_capture_vision_flutter*. Including the *dynamsoft_barcode_reader_bundle_flutter* library will automatically include the *dynamsoft_capture_vision_flutter* library.


## API Overview

### BarcodeScanner

[`BarcodeScanner`](barcode-scanner.md) is the main class of the Ready-to-Use edition of the library and contains the API needed to implement the barcode scanning functionality. Please visit the BarcodeScanner Class page to learn about how this class operates.

> [!TIP]
> To learn how to implement the Barcode Reader using the BarcodeScanner API, please read through the [Barcode Reader Integration Guide (Ready-To-Use Edition)](../user-guide.md).

### BarcodeScannerConfig

[`BarcodeScannerConfig`](barcode-scanner-config.md) is the class that defines the configurations for the Barcode Scanner. These configurations can be from a performance related or UI related. Even though the full set of parameters of the Barcode Reader is not exposed in this class, they can still be set via a JSON template - allowing the developer to fully customize the Barcode Reader's performance while still making use of the benefits of the Ready-To-Use API.

> [!TIP]
> To learn how to configure the BarcodeScanner instance using the BarcodeScannerConfig class, please visit this [section of the Ready-To-Use Guide](../../user-guide.md#configuring-the-barcodescanner-optional).

### BarcodeScanResult

[`BarcodeScanResult`](barcode-scan-result.md) is a result class that contains all the decoded barcodes and their associated info. This class is dependent on the [`BarcodeResultItem`](../capture-vision-router-lite/barcode-result-item.md) class which is part of the Capture Vision Foundational API.

