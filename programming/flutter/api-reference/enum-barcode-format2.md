---
layout: default-layout
title: EnumBarcodeFormat_2 of Dynamsoft Capture Vision Flutter Edition
description: The second group enumeration of the barcode formats of Dynamsoft Capture Vision Flutter edition.
keywords: Barcode format, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumBarcodeFormat_2
---

# EnumBarcodeFormat_2

`EnumBarcodeFormat_2` is the second group of barcode formats.

```dart
enum EnumBarcodeFormat_2 {
    static const int BF2_NONSTANDARD_BARCODE = 0x01; // Nonstand barcode.
    static const int BF2_DOTCODE = 0x02; // Dot code.
    static const int BF2_PHARMACODE = 0x0C; // Pharma code.
    static const int BF2_PHARMACODE_ONE_TRACK = 0x04; // Pharma code - one track.
    static const int BF2_PHARMACODE_TWO_TRACK = 0x08; // Pharma code - two track.
    static const int BF2_POSTALCODE = 0x01F00000; // Postal code.
    static const int BF2_POSTNET = 0x00200000; // Postnet code.
    static const int BF2_PLANET = 0x00400000; // Planet code.
    static const int BF2_AUSTRALIANPOST = 0x00800000; // Australian post code.
    static const int BF2_RM4SCC = 0x01000000; // RM4SCC code.
    static const int BF2_USPSINTELLIGENTMAIL = 0x00100000; // USPS Intelligent Mail code.
    static const int BF2_NULL = 0x00; // Disable all barcode formats in group 2.
}
```

## Related API(s)

- [`DCVBarcodeReader.updateRuntimeSettings`](barcode-reader.md#updateruntimesettings)
- [`DBRRuntimeSettings`](class-dbr-runtime-settings.md)
- [`EnumBarcodeFormat`](enum-barcode-format.md)
