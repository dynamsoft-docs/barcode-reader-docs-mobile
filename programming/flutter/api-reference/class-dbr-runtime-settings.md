---
layout: default-layout
title: Class DBRRuntimeSettings of Dynamsoft Capture Vision Flutter Edition
description: Documentation page of class of DBR runtime settings of Dynamsoft Capture Vision.
keywords: Class DBRRuntimeSettings, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: DBRRuntimeSettings
---

# DBRRuntimeSettings

Class `DBRRuntimeSettings`. It stores the basic barcode decoding settings when using Dynamsoft Barcode Reader.

```dart
class DBRRuntimeSettings extends Serializer{
    /// Sets the formats of the barcode in BarcodeFormat group 1 to be read. Barcode formats in BarcodeFormat group 1 can be combined.
    int? barcodeFormatIds;

    /// Sets the formats of the barcode in BarcodeFormat group 2 to be read. Barcode formats in BarcodeFormat group 2 can be combined.
    int? barcodeFormatIds_2;

    /// Sets the number of barcodes expected to be detected for each image.
    int? expectedBarcodeCount;

    /// Sets the maximum amount of time (in milliseconds) that should be spent searching for a barcode per page.
    int? timeout;

    /// Filter the barcode results by the minimum length of barcode text.
    int? minBarcodeTextLength;

    /// Filter the barcode results by the minimum confidence.
    int? minResultConfidence;

    /// This parameter helps control the process of binarization
    /// Added in version 1.2.0
    List<int>? binarizationModes;

    /// Sets the mode and priority for deblurring.
    /// Added in version 1.2.0
    List<int>? deblurModes;

    /// A simplified way to set deblur modes with int from 0 to 9.
    /// Added in version 1.2.0
    int? deblurLevel;

    /// LocalizationModes determines how to localize barcodes.
    /// Added in version 1.2.0
    List<int>? localizationModes;

    /// ScaleUpModes determines the process for scaling up an image used for detecting barcodes with small module size.
    /// Added in version 1.2.0
    List<int>? scaleUpModes;

    /// BarcodeResults are returned in a array. TextResultOrderModes defines how the BarcodeResults are ordered.
    /// Added in version 1.2.0
    List<int>? textResultOrderModes;

    /// ScaleDownThreshold defines the threshold for image shrinking.
    /// Added in version 1.2.0
    int? scaleDownThreshold;

    /// Region defines a region in where to search barcodes.
    /// Added in version 1.2.0
    Region? region;

    /// Further modes settings. Please read more in FurtherModes class.
    /// Added in version 1.2.0
    FurtherModes? furtherModes;
}
```

You can find detailed instructions of the mode parameters on **Dynamsoft Barcode Reader** documents

- <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/binarization-modes.html" target="_blank">binarizationModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/deblur-modes.html" target="_blank">deblurModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/localization-modes.html" target="_blank">localizationModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/region.html" target="_blank">region</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/scale-down-threshold.html" target="_blank">scaleDownThreshold</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/scale-up-modes.html" target="_blank">scaleUpModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/reference/text-result-order-modes.html" target="_blank">textResultOrderModes</a>

## Related API(s)

- [`updateRuntimeSettings`](barcode-reader.md#updateruntimesettings)
- [`EnumBarcodeFormat`](enum-barcode-format.md)
- [`EnumBarcodeFormat_2`](enum-barcode-format2.md)
