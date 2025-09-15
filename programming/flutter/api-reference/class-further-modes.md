---
layout: default-layout
title: Class FurtherModes of Dynamsoft Capture Vision Flutter Edition
description: The class of DBR runtime settings
keywords: Class FurtherModes, API Reference, Flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: FurtherModes
---

# FurtherModes

> *Added in version 1.2.0.*

Class `FurtherModes`. Configure the furtherModes to set when using Dynamsoft Barcode Reader.

```dart
class FurtherModes {
    /// Sets the mode and priority for the barcode colour mode used to process the barcode zone.
    List<int>? barcodeColourModes;

    /// Sets the mode and priority to complement the missing parts in the barcode.
    List<int>? barcodeComplementModes;
    
    /// Sets the mode and priority for colour categorization. To be supported.
    List<int>? colourClusteringModes;
    
    /// Sets the mode and priority for converting a colour image to a grayscale image.
    List<int>? colourConversionModes;
    
    /// Sets the mode and priority for deformation resisting.
    List<int>? deformationResistingModes;
    
    /// Sets the mode and priority for DPM code reading.
    List<int>? dpmCodeReadingModes;
    
    /// Sets the mode and priority for the grayscale image conversion.
    List<int>? grayscaleTransformationModes;
    
    /// Sets the mode and priority for image preprocessing algorithms.
    List<int>? imagePreprocessingModes;
    
    /// Sets the region pre-detection mode for barcodes searching.
    List<int>? regionPredetectionModes;
    
    /// Sets the mode and priority for texture detection.
    List<int>? textureDetectionModes;
    
    /// Sets the mode and priority for text filter.
    List<int>? textFilterModes;
}
```

You can find detailed instructions of the mode parameters on **Dynamsoft Barcode Reader** documents

- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/barcode-colour-modes.html" target="_blank">barcodeColourModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/barcode-complement-modes.html" target="_blank">barcodeComplementModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/colour-clustering-modes.html" target="_blank">colourClusteringModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/colour-conversion-modes.html" target="_blank">colourConversionModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/deformation-resisting-modes.html" target="_blank">deformationResistingModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/dpm-code-reading-modes.html" target="_blank">dpmCodeReadingModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/grayscale-transformation-modes.html" target="_blank">grayscaleTransformationModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/image-preprocessing-modes.html" target="_blank">imagePreprocessingModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/region-predetection-modes.html" target="_blank">regionPredetectionModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/texture-detection-modes.html" target="_blank">textureDetectionModes</a>
- <a href="https://www.dynamsoft.com/barcode-reader/docs-archive/core/parameters/reference/text-filter-modes.html" target="_blank">textFilterModes</a>

## Related API(s)

- [`updateRuntimeSettings`](barcode-reader.md#updateruntimesettings)
- [`EnumBarcodeFormat`](enum-barcode-format.md)
- [`EnumBarcodeFormat_2`](enum-barcode-format2.md)
