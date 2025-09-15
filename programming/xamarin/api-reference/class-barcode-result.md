---
layout: default-layout
title: Class BarcodeResult of Dynamsoft Capture Vision Xamarin Edition
description: The class of BarcodeResult result
keywords: Class BarcodeResult, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: BarcodeResult
---

# BarcodeResult

Class `BarcodeResult`. The return value when a barcode is detected. It stores the barcode information including barcode text and barcode formats.

```c#
namespace DCVXamarin
{
    public class BarcodeResult
    {
        // The barcode text.
        public string BarcodeText { get; set; }

        // The barcode decoding result in bytes.
        public byte[] BarcodeBytes { get; set; }

        // Barcode type in string.
        public string BarcodeFormatString { get; set; }

        // The corresponding localization result.
        public BarcodeLocationResult BarcodeLocationResult { get; set; }
    }
}
```

## Related API(s)

- [`DCVBarcodeReader.AddResultListener`](barcode-reader.md#addresultlistener)
- [`Class BarcodeLocationResult`](class-barcode-location-result.md)
- [`Class Quadrilateral`](class-quadrilateral.md)
