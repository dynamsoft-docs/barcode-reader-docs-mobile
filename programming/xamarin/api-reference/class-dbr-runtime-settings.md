---
layout: default-layout
title: Class DBRRuntimeSettings of Dynamsoft Capture Vision Xamarin Edition
description: DBRRuntimeSettings class of DCV Xamarin Edition defines the barcode decoding settings.
keywords: Class DBRRuntimeSettings, API Reference, Xamarin, Xamarin Forms
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: DBRRuntimeSettings
---

# DBRRuntimeSettings

Class `DBRRuntimeSettings`. It stores the basic barcode decoding settings when using Dynamsoft Barcode Reader.

```c#
namespace DCVXamarin
{
    public class DBRRuntimeSettings
    {
        // Sets the formats of the barcode in BarcodeFormat group 1 to be read. Barcode formats in BarcodeFormat group 1 can be combined.
        // Default value: BF_ALL;
        public EnumBarcodeFormat BarcodeFormatIds { get; set; }

        // Sets the formats of the barcode in BarcodeFormat group 2 to be read. Barcode formats in BarcodeFormat group 1 can be combined.
        // Default value: null;
        public EnumBarcodeFormat_2 BarcodeFormatIds_2 { get; set; }

        // Sets the number of barcodes expected to be detected for each image.
        // Default value: 1;
        // Range: [0, 0x7fffffff];
        public int ExpectedBarcodeCount { get; set; }

        // Sets the maximum amount of time (in milliseconds) that should be spent searching for a barcode per page.
        // Default value: 500;
        // Range: [0, 0x7fffffff];
        public int Timeout { get; set; }

        // Set the minimum confidence of the output barcode result. The result with lower confidence will not be returned.
        // Default value: 30;
        // Range: [0, 100];
        public int MinResultConfidence { get; set; }

        // Set the minimum text length of the output barcode result. The shorter result will not be returned.
        // Default value: 0;
        // Range: [0, 0x7fffffff];
        public int MinBarcodeTextLength { get; set; }
    }
}
```

## Related API(s)

- [`updateRuntimeSettings`](barcode-reader.md#updateruntimesettingsdbrruntimesettings): Update the `DBRRuntimeSettings`.
- [`EnumBarcodeFormat`](enum-barcode-format.md): The first group of the supported barcode format. It contains the majority of common barcode formats. You can use this enumeration to specify the `BarcodeFormatIds` parameter of `DBRRuntimeSettings`.
- [`EnumBarcodeFormat_2`](enum-barcode-format2.md): The second group of the supported barcode format. It contains some specific barcode formats. You can use this enumeration to specify the `BarcodeFormatIds_2` parameter of `DBRRuntimeSettings`.
