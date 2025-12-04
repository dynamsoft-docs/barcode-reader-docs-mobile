---
layout: default-layout
title: BarcodeScanner Class - Dynamsoft Barcode Reader React Native Edition
description: BarcodeScanner of DynamsoftBarcodeScanner React Native is an activity class that implements barcode scanning features.
keywords: Barcode, scanner, activity
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScanner
---

# BarcodeScanner Class

`BarcodeScanner` is the main class of the Ready-to-Use edition of the library and contains the API needed to implement the barcode scanning functionality.

## Definition

*Assembly:* dynamsoft-barcode-reader-bundle-react-native

```js
class BarcodeScanner
```

## Methods

### launch

This function initiates the barcode scanning process by launching a new page (Activity on Android/ViewController on iOS) that displays the camera stream and any other associated UI elements that help with the scanning process. The launch method accepts an optional [`BarcodeScannerConfig`](barcode-scanner-config.md) configuration object that allows the developer to customize the scanner's behaviour and UI. 

```js
static async launch(config?: BarcodeScanConfig): Promise<BarcodeScanResult>
```

**Parameters**

`config`: Configuration parameters for the barcode scanner

> [!Note]
> A valid Barcode Reader license is required to operate. You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile) link.

**Returns**

Promise that resolves with the scan result as a [`BarcodeScanResult`](barcode-scan-result.md) object.

- If the scan is successful, the Promise resolves with the scan result.
- If an error occurs during the scan, the Promise rejects with an error message.
- If the user manually exits the scanner, the Promise resolves with `null`.
