---
layout: default-layout
title: Class BarcodeResult of Dynamsoft Capture Vision Flutter Edition
description: Documentation page of the class of BarcodeResult result of Dynamsoft Capture Vision.
keywords: Class BarcodeResult, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: BarcodeResult
---

# BarcodeResult

Class `BarcodeResult`. The return value when a barcode is detected. It stores the barcode information including barcode text and barcode formats.

```dart
class BarcodeResult {
  /// The barcode text.
  final String barcodeText;

  /// The byte of barcode text.
  final Uint8List barcodeBytes;

  /// Barcode type in string.
  final String barcodeFormatString;

  /// The corresponding localization result.
  final BarcodeLocationResult barcodeLocation;
}
```

## Related API(s)

- [`DCVBarcodeReader.receiveResultStream`](barcode-reader.md#receiveresultstream)
- [`Class BarcodeLocationResult`](class-barcode-location-result.md)
- [`Class Quadrilateral`](class-quadrilateral.md)
- [`Class Point`](class-point.md)
