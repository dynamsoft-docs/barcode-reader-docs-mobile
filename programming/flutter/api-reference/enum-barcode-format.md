---
layout: default-layout
title: EnumBarcodeFormat of Dynamsoft Capture Vision Flutter Edition
description: The first group enumeration of the barcode formats of Dynamsoft Capture Vision Flutter edition.
keywords: Barcode format, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumBarcodeFormat
---

# EnumBarcodeFormat

`EnumBarcodeFormat` is the first group of barcode formats.

```dart
class EnumBarcodeFormat{
    static const int BF_ALL = -29360129; // The combination of all barcode formats in group 1.
    static const int BF_ONED = 0x003007FF; // The combination of all oneD barcode formats.
    static const int BF_GS1_DATABAR = 0x0003F800; // The combination of all GS1 databar.
    static const int BF_CODE_39 = 0x1; // Code 39, one of the oneD barcode formats.
    static const int BF_CODE_128 = 0x2; // Code 128, one of the oneD barcode formats.
    static const int BF_CODE_93 = 0x4; // Code 93, one of the oneD barcode formats.
    static const int BF_CODABAR = 0x8; // Codebar, one of the oneD barcode formats.
    static const int BF_CODE_11 = 0x200000; // Code 11, one of the oneD barcode formats.
    static const int BF_ITF = 0x10; // ITF, one of the oneD barcode formats.
    static const int BF_EAN_13 = 0x20; // EAN 13, one of the oneD barcode formats.
    static const int BF_EAN_8 = 0x40; // EAN 8, one of the oneD barcode formats.
    static const int BF_UPC_A = 0x80; // UPC A, one of the oneD barcode formats.
    static const int BF_UPC_E = 0x100; // UPC_E, one of the oneD barcode formats.
    static const int BF_INDUSTRIAL_25 = 0x200; // Industrial 25, one of the oneD barcode formats.
    static const int BF_CODE_39_EXTENDED = 0x400; // Code 39 extended, one of the oneD barcode formats.
    static const int BF_GS1_DATABAR_OMNIDIRECTIONAL = 0x800; // One of the GS1 databar.
    static const int BF_GS1_DATABAR_TRUNCATED = 0x1000; // One of the GS1 databar.
    static const int BF_GS1_DATABAR_STACKED = 0x2000; // One of the GS1 databar.
    static const int BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL = 0x4000; // One of the GS1 databar.
    static const int BF_GS1_DATABAR_EXPANDED = 0x8000; // One of the GS1 databar.
    static const int BF_GS1_DATABAR_EXPANDED_STACKED = 0x10000; // One of the GS1 databar.
    static const int BF_GS1_DATABAR_LIMITED = 0x20000; // One of the GS1 databar.
    static const int BF_PATCHCODE = 0x00040000; // Patch code.
    static const int BF_PDF417 = 0x02000000; // PDF 417.
    static const int BF_QR_CODE = 0x04000000; // QR code.
    static const int BF_DATAMATRIX = 0x08000000; // Data matrix code.
    static const int BF_AZTEC = 0x10000000; // AZTEC code.
    static const int BF_MAXICODE = 0x20000000; // MAXI code.
    static const int BF_MICRO_QR = 0x40000000; // Micro QR code.
    static const int BF_MICRO_PDF417 = 0x00080000; // Micro PDF417 code.
    static const int BF_GS1_COMPOSITE = -2147483648; // GS1 composite code.
    static const int BF_MSI_CODE = 0x100000; // MSI code.
    static const int BF_NULL = 0x00; // Disable all barcode formats in group 1.
}
```

## Related API(s)

- [`DCVBarcodeReader.updateRuntimeSettings`](barcode-reader.md#updateruntimesettings)
- [`DBRRuntimeSettings`](class-dbr-runtime-settings.md)
- [`EnumBarcodeFormat_2`](enum-barcode-format2.md)
