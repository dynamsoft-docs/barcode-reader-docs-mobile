---
layout: default-layout
title: BarcodeScanner Class - Dynamsoft Barcode Reader Flutter Edition
description: BarcodeScanner of DynamsoftBarcodeScanner Flutter is an activity class that implements barcode scanning features.
keywords: Barcode, scanner, activity
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScanner
---

# BarcodeScanner Class

`BarcodeScanner` is the main class of the Ready-to-Use edition of the library and contains the API needed to implement the barcode scanning functionality.

## Definition

*Assembly:* dynamsoft_barcode_reader_bundle_flutter

```dart
class BarcodeScanner
```

## Constructor

```dart
BarcodeScanner.new()
```

## Methods

### launch

This function initiates the barcode scanning process by launching a new page (Activity on Android/ViewController on iOS) that displays the camera stream and any other associated UI elements that help with the scanning process. The launch method accepts an optional [`BarcodeScannerConfig`](barcode-scanner-config.md) configuration object that allows the developer to customize the scanner's behaviour and UI. 

```dart
Future<BarcodeScanResult> launch(BarcodeScannerConfig config)
```

#### Returns

A `Future<BarcodeScanResult>` that resolves with the [`BarcodeScanResult`](barcode-scan-result.md) when the scanner is closed.

#### Remarks

Please note that the launch method needs a valid Barcode Reader license in order to operate. You can request a 30-day trial license via the [Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dbr&utm_source=guide&package=mobile) portal.

#### Code Snippet

```dart
import 'package:dynamsoft_barcode_reader_bundle_flutter/dynamsoft_barcode_reader_bundle_flutter.dart';

void _launchBarcodeScanner() async{
  var config = BarcodeScannerConfig(
    license: 'YOUR_LICENSE_KEY_HERE',
  );
  BarcodeScanResult result = await BarcodeScanner.launch(config);
  if(result.status == EnumResultStatus.finished){
    // handle the result
  }
}
```
