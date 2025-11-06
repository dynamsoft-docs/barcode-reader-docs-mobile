---
layout: default-layout
title: EnumLocalizationMode - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumLocalizationMode of DBR Flutter Edition specifies the strategies used to identify the locations of barcodes within an image.
keywords: localization, Flutter, settings, performance, barcode reader
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumLocalizationMode
---

# EnumLocalizationMode

`EnumLocalizationMode` is an enumeration that represents the strategies used to identify the location of barcodes within an image or frame. Localization is one of the first and most important steps in the barcode detection process, so choosing the right localization modes for the scenario can make quite the difference in performance. 

> [!NOTE]
> Some localization modes are optimized for certain barcode formats as you can see in the description of each mode below. However, it is recommended to have the `connectedBlocks` mode as the highest priority localization mode for any scenario as it is one most highly adaptable localization algorithms for any kind of scenario.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumLocalizationMode {
    skip,
    auto,
    connectedBlocks,
    statistics,
    lines,
    scanDirectly,
    statisticsMarks,
    statisticsPostalCode,
    centre,
    oneDFastScan,
    neuralNetwork,
    end
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `skip` | Omits the localization process entirely. |
| `auto` | Automatic localization mode selection; not yet implemented so this is a placeholder until then. |
| `connectedBlocks` | Identifies barcodes by finding connected blocks, offering optimal results, especially recommended for highest priority in most scenarios. |
| `statistics` | Detects barcodes through analysis of patterns of contiguous black and white regions, tailored for QR Codes and DataMatrix codes. |
| `lines` | Locates barcodes by identifying linear patterns, designed primarily for 1D barcodes and PDF417 codes. |
| `scanDirectly` | Provides rapid barcode localization, suited for interactive applications where speed is crucial. |
| `statisticsMarks` | Targets barcode localization through detection of specific mark groups, optimized for Direct Part Marking (DPM) codes. |
| `statisticsPostalCode` | Combines methods of locating connected blocks and linear patterns to efficiently localize postal codes. |
| `centre` | Initiates barcode localization from the image center, facilitating faster detection in certain layouts. |
| `oneDFastScan` | Specialized for quick localization of 1D barcodes, enhancing performance in fast-scan scenarios. |
| `neuralNetwork` | Localizes barcodes by utilizing a neural network model. |
| `end` | Placeholder value with no functional meaning. |

> [!NOTE]
> To learn about the localization modes in depth, please visit the full [LocalizationModes Parameter]({{ site.dcvb_parameters }}reference/barcode-reader-task-settings/localization-modes.html?q=localizationmodes#candidate-modes-descriptions) page.
