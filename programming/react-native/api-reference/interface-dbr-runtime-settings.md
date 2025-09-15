---
layout: default-layout
title: Interface DBRRuntimeSettings - Dynamsoft Capture Vision React Native Edition
description: The interface of DBR runtime settings of Dynamsoft Capture Vision React Native edition.
keywords: Interface DBRRuntimeSettings, API reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: DBRRuntimeSettings
---

# DBRRuntimeSettings

Interface `DBRRuntimeSettings`. It stores the basic barcode decoding settings when using Dynamsoft Barcode Reader.

```js
export interface DBRRuntimeSettings {
    /**
     * Sets the formats of the barcode in BarcodeFormat group 1 to be read. Barcode formats in BarcodeFormat group 1 can be combined.
     */
    barcodeFormatIds: number;
    /**
     * Sets the formats of the barcode in BarcodeFormat group 2 to be read. Barcode formats in BarcodeFormat group 2 can be combined.
     */
    barcodeFormatIds_2: number;
    /**
     * Sets the number of barcodes expected to be detected for each image.
     */
    expectedBarcodeCount: number;
    /**
     * Sets the maximum amount of time (in milliseconds) that should be spent searching for a barcode per page.
     */
    timeout: number;
}
```

## Related API(s)

- [`updateRuntimeSettings`](barcode-reader.md#updateruntimesettings)
- [`EnumBarcodeFormat`](enum-barcode-format.md)
- [`EnumBarcodeFormat_2`](enum-barcode-format2.md)
