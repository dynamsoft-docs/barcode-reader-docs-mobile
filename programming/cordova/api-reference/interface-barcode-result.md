---
layout: default-layout
title: Interface BarcodeResult of Dynamsoft Capture Vision Cordova Edition
description: The interface of BarcodeResult
keywords: Interface BarcodeResult, API Reference, Cordova
needAutoGenerateSidebar: false
needGenerateH3Content: false
noTitleIndex: true
breadcrumbText: BarcodeResult
---

# BarcodeResult

Interface `BarcodeResult`. It stores the barcode information including barcode text and barcode formats.

```js
export interface BarcodeResult {
    // The barcode text.
    barcodeText: string;

    // The Base64 string that stores the barcode bytes.
    barcodeBytes: string;

    // Barcode type in string.
    barcodeFormatString: string;
    
    // The corresponding localization result.
    barcodeLocation: BarcodeLocationResult;
}
```

## Related API(s)

- [`DCVBarcodeReader.addResultListener`](barcode-reader.md#addresultlistener)
- [`Interface BarcodeLocationResult`](interface-barcode-location-result.md)
