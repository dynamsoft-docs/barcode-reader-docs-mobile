---
layout: default-layout
title: EnumLocalizationMode - Dynamsoft Barcode Reader React Native
description: Enumeration EnumLocalizationMode of DBR React Native Edition specifies the strategies used to identify the locations of barcodes within an image.
keywords: localization, React Native, settings, performance, barcode reader
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumLocalizationMode
---

# EnumLocalizationMode

`EnumLocalizationMode` is an enumeration that represents the strategies used to identify the location of barcodes within an image or frame. Localization is one of the first and most important steps in the barcode detection process, so choosing the right localization modes for the scenario can make quite the difference in performance. 

> [!NOTE]
> Some localization modes are optimized for certain barcode formats as you can see in the description of each mode below. However, it is recommended to have the `connectedBlocks` mode as the highest priority localization mode for any scenario as it is one most highly adaptable localization algorithms for any kind of scenario.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```tsx
enum EnumLocalizationMode {
    LM_END = -1,
    LM_SKIP = 0x0,
    LM_AUTO = 0x1,
    LM_CONNECTED_BLOCKS = 0x2,
    LM_STATISTICS = 0x4,
    LM_LINES = 0x8,
    LM_SCAN_DIRECTLY = 0x10,
    LM_STATISTICS_MARKS = 0x20,
    LM_STATISTICS_POSTAL_CODE = 0x40,
    LM_CENTRE = 0x80,
    LM_ONED_FAST_SCAN = 0x100,
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `LM_SKIP` | Omits the localization process entirely. |
| `LM_AUTO` | Automatic localization mode selection; not yet implemented so this is a placeholder until then. |
| `LM_CONNECTED_BLOCKS` | Identifies barcodes by finding connected blocks, offering optimal results, especially recommended for highest priority in most scenarios. |
| `LM_STATISTICS` | Detects barcodes through analysis of patterns of contiguous black and white regions, tailored for QR Codes and DataMatrix codes. |
| `LM_LINES` | Locates barcodes by identifying linear patterns, designed primarily for 1D barcodes and PDF417 codes. |
| `LM_SCAN_DIRECTLY` | Provides rapid barcode localization, suited for interactive applications where speed is crucial. |
| `LM_STATISTICS_MARKS` | Targets barcode localization through detection of specific mark groups, optimized for Direct Part Marking (DPM) codes. |
| `LM_STATISTICS_POSTAL_CODE` | Combines methods of locating connected blocks and linear patterns to efficiently localize postal codes. |
| `LM_CENTRE` | Initiates barcode localization from the image center, facilitating faster detection in certain layouts. |
| `LM_ONED_FAST_SCAN` | Specialized for quick localization of 1D barcodes, enhancing performance in fast-scan scenarios. |
| `LM_NEURAL_NETWORK` | Localizes barcodes by utilizing a neural network model. |
| `LM_END` | Placeholder value with no functional meaning. |

> [!NOTE]
> View more about [LocalizationModes Parameters]({{ site.dcv_parameters_reference }}barcode-reader-task-settings/localization-modes.html) page.
