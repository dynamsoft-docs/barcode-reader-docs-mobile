---
layout: default-layout
title: EnumScanningMode - Dynamsoft Barcode Reader Flutter Edition
description: EnumScanningMode of DynamsoftBarcodeReader Flutter is an enumeration class that defines the scanning mode.
keywords: BarcodeScanner, ScanningMode, flutter, 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumScanningMode
---

# EnumScanningMode

`EnumScanningMode` is a enumeration class that determines the scanning mode that the `BarcodeScanner` instance will operate in.

## Definition

*Assembly:* dynamsoft_barcode_reader_bundle_flutter

```dart
enum EnumScanningMode 
{
    single, // used for scanning a single barcode at a time, prioritizing speed over read rate
    multiple // used for scanning multiple barcodes at a time, finding a balance between speed and read rate
}
```
