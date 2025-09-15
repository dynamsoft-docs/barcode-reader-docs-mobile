---
layout: default-layout
title: EnumBarcodeFormat of Dynamsoft Capture Vision Cordova Edition
description: Documentation page of first group enumeration of the barcode formats of Dynamsoft Capture Vision.
keywords: Barcode format, API Reference, Cordova
needAutoGenerateSidebar: false
needGenerateH3Content: false
noTitleIndex: true
breadcrumbText: EnumBarcodeFormat
---

# EnumBarcodeFormat

`EnumBarcodeFormat` is the first group of barcode formats.

```js
export enum EnumBarcodeFormat {
    BF_ALL = 0xFE3FFFFF, // The combination of all barcode formats in group 1.
    BF_ONED = 0x3007FF, // The combination of all oneD barcode formats.
    BF_GS1_DATABAR = 0x3F800, // The combination of all GS1 databar.
    BF_CODE_39 = 0x1, // Code 39, one of the oneD barcode formats.
    BF_CODE_128 = 0x2, // Code 128, one of the oneD barcode formats.
    BF_CODE_93 = 0x4, // Code 93, one of the oneD barcode formats.
    BF_CODABAR = 0x8, // Codebar, one of the oneD barcode formats.
    BF_CODE_11 = 0x200000, // Code 11, one of the oneD barcode formats.
    BF_ITF = 0x10, // ITF, one of the oneD barcode formats.
    BF_EAN_13 = 0x20, // EAN 13, one of the oneD barcode formats.
    BF_EAN_8 = 0x40, // EAN 8, one of the oneD barcode formats.
    BF_UPC_A = 0x80, // UPC A, one of the oneD barcode formats.
    BF_UPC_E = 0x100, // UPC_E, one of the oneD barcode formats.
    BF_INDUSTRIAL_25 = 0x200, // Industrial 25, one of the oneD barcode formats.
    BF_CODE_39_EXTENDED = 0x400, // Code 39 extended, one of the oneD barcode formats.
    BF_GS1_DATABAR_OMNIDIRECTIONAL = 0x800, // One of the GS1 databar.
    BF_GS1_DATABAR_TRUNCATED = 0x1000, // One of the GS1 databar.
    BF_GS1_DATABAR_STACKED = 0x2000, // One of the GS1 databar.
    BF_GS1_DATABAR_STACKED_OMNIDIRECTIONAL = 0x4000, // One of the GS1 databar.
    BF_GS1_DATABAR_EXPANDED = 0x8000, // One of the GS1 databar.
    BF_GS1_DATABAR_EXPANDED_STACKED = 0x10000, // One of the GS1 databar.
    BF_GS1_DATABAR_LIMITED = 0x20000, // One of the GS1 databar.
    BF_PATCHCODE = 0x40000, // Patch code.
    BF_PDF417 = 0x2000000, // PDF 417.
    BF_QR_CODE = 0x4000000, // QR code.
    BF_DATAMATRIX = 0x8000000, // Data matrix code.
    BF_AZTEC = 0x10000000, // AZTEC code.
    BF_MAXICODE = 0x20000000, // MAXI code.
    BF_MICRO_QR = 0x40000000, // Micro QR code.
    BF_MICRO_PDF417 = 0x80000, // Micro PDF417 code.
    BF_GS1_COMPOSITE = 0x80000000, // GS1 composite code.
    BF_MSI_CODE = 0x100000, // MSI code.
    BF_NULL = 0x00 // Disable all barcode formats in group 1.
}
```

## Related API(s)

- [`DCVBarcodeReader.updateRuntimeSettings`](barcode-reader.md#updateruntimesettingsdbrruntimesettings)
- [`DBRRuntimeSettings`](interface-dbr-runtime-settings.md)
- [`EnumBarcodeFormat_2`](enum-barcode-format2.md)
