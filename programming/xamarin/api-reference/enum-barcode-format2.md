---
layout: default-layout
title: EnumBarcodeFormat_2 of Dynamsoft Capture Vision Xamarin Edition
description: The second group enumeration of the barcode formats of Dynamsoft Capture Vision Xamarin.Forms edition.
keywords: Barcode format, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: EnumBarcodeFormat_2
---

# EnumBarcodeFormat_2

`EnumBarcodeFormat_2` is the second group of barcode formats.

```c#
namespace DCVXamarin
{
    public enum EnumBarcodeFormat_2 : long
    {
        BF_NULL = 0x00 // Disable all barcode formats in group 1.
        BF2_NONSTANDARD_BARCODE = 0x01, // Nonstand barcode.
        BF2_DOTCODE = 0x02, // Dot code.
        BF2_PHARMACODE = 0x0c, // Pharma code.
        BF2_PHARMACODE_ONE_TRACK = 0x04, // Pharma code - one track.
        BF2_PHARMACODE_TWO_TRACK = 0x08, // Pharma code - two track.
        BF2_USPSINTELLIGENTMAIL = 0x00100000, // USPS Intelligent Mail code.
        BF2_POSTNET = 0x00200000, // Postnet code.
        BF2_PLANET = 0x00400000, // Planet code.
        BF2_AUSTRALIANPOST = 0x00800000, // Australian post code.
        BF2_RM4SCC = 0x01000000, // RM4SCC code.
        BF2_POSTALCODE = 0x01F00000, // Postal code.
    }
}
```

## Related API(s)

- [`IDCVBarcodeReader.updateRuntimeSettings`](barcode-reader.md#updateruntimesettings)
- [`DBRRuntimeSettings`](class-dbr-runtime-settings.md)
- [`EnumBarcodeFormat`](enum-barcode-format.md)
