---
layout: default-layout
title: DSSimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader Android Edition
description: DSSimplifiedBarcodeReaderSettings class contains settings for barcode decoding. It is a sub-parameter of DSSimplifiedCaptureVisionSettings
keywords: DSSimplifiedBarcodeReaderSettings, DSSimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSSimplifiedBarcodeReaderSettings
permalink: /programming/android/api-reference/simplified-barcode-reader-settings.html
---

# DSSimplifiedBarcodeReaderSettings

The `DSSimplifiedBarcodeReaderSettings` struct contains settings for barcode decoding. It is a sub-parameter of [`DSSimplifiedCaptureVisionSettings`]({{ site.dcv_android_api }}capture-vision-router/structs/simplified-capture-vision-settings.html)

## Definition

```cpp
typedef struct tagSimplifiedBarcodeReaderSettings
{
    unsigned long long barcodeFormatIds;
    int expectedBarcodesCount;
    GrayscaleTransformationMode grayscaleTransformationModes[8];
    GrayscaleEnhancementMode grayscaleEnhancementModes[8];
    LocalizationMode localizationModes[8];
    DeblurMode deblurModes[10];
    int minResultConfidence;
    int minBarcodeTextLength;
    char barcodeTextRegExPattern[256];
    int maxThreadsInOneTask;
    char reserved[512];
} SimplifiedBarcodeReaderSettings;
```

## Attributes

| Attribute | Type |
| --------- | ---- |
| [`barcodeFormatIds`](#barcodeformatids) | *unsigned long long* |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *GrayscaleTransformationMode[8]* |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *GrayscaleEnhancementMode[8]* |
| [`localizationModes`](#localizationmodes) | *LocalizationMode[8]* |
| [`deblurModes`](#deblurmodes) | *DeblurMode[10]* |
| [`minResultConfidence`](#minresultconfidence) | *int* |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *char* |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* |
| [`reserved`](#reserved) | *char[512]* |

### barcodeFormatIds

Input a combined value of enumeration [`BarcodeFormat`]({{ site.dcv_enumerations }}barcode-reader/barcode-format.html?lang=android) to specify the targeting barcode formats.

```cpp
unsigned long long barcodeFormatIds;
```

### expectedBarcodesCount

Set the expected barcode count. The default value is 0.

```cpp
int expectedBarcodesCount;
```

**Remarks**

* Set `expectedBarcodesCount` to 0 if the barcode count is unknown. The library will try to find at least 1 barcode.
* Set `expectedBarcodesCount` to 1 to reach the highest speed for processing single barcode.
* Set `expectedBarcodesCount` to "n" if there will be "n" barcodes to process from an image.
* Set `expectedBarcodesCount` to the highest expected value if there exists multiple barcode but the exact count is not confirmed.

### grayscaleTransformationModes

Set the grayscale transformation modes with an array of enumeration [`GrayscaleTransformationMode`]({{ site.dcv_enumerations }}core/grayscale-transformation-mode.html?lang=android). View the reference page of <a href="{{ site.dcv_parameters_reference }}image-parameter/grayscale-transformation-modes.html?product=dbr&repoType=core" target="_blank">`GrayscaleTransformationModes`</a> for more detail about grayscale transformation modes.

```cpp
GrayscaleTransformationMode grayscaleTransformationModes[8];
```

### grayscaleEnhancementModes

Set the grayscale enhancement modes with an array of enumeration [`GrayscaleEnhancementMode`]({{ site.dcv_enumerations }}core/grayscale-enhancement-mode.html?lang=android). View the reference page of <a href="{{ site.dcv_parameters_reference }}image-parameter/grayscale-enhancement-modes.html?product=dbr&repoType=core" target="_blank">`GrayscaleEnhancementModes`</a> for more detail about grayscale enhancement modes.

```cpp
GrayscaleEnhancementMode grayscaleEnhancementModes[8];
```

### localizationModes

Set the location modes with an array of enumeration [`LocalizationMode`]({{ site.dcv_enumerations }}barcode-reader/localization-mode.html?lang=android). View the reference page of <a href="{{ site.dcv_parameters_reference }}barcode-reader-task-settings/localization-modes.html?product=dbr&repoType=core" target="_blank">`LocalizationModes`</a> for more detail about location modes.

```cpp
LocalizationMode localizationModes[8];
```

### deblurModes

Set the deblur modes with an array of enumeration [`DeblurMode`]({{ site.dcv_enumerations }}barcode-reader/deblur-mode.html?lang=android). View the reference page of <a href="{{ site.dcv_parameters_reference }}barcode-reader-task-settings/deblur-modes.html?product=dbr&repoType=core" target="_blank">`DeblurModes`</a> for more detail about deblur modes.

```cpp
DeblurMode deblurModes[10];
```

### minResultConfidence

Set the minimum result confidence to filter out the low confidence results. The default value is 30.

```cpp
int minResultConfidence;
```

### minBarcodeTextLength

Set the minimum barcode text length to filter out the unqualified results.

```cpp
int minBarcodeTextLength;
```

### barcodeTextRegExPattern

Set the RegEx pattern of the barcode text to filter out the unqualified results.

```cpp
char barcodeTextRegExPattern[256];
```

### maxThreadsInOneTask

Set the maximum available threads count in one barcode decoding task.

```cpp
int maxThreadsInOneTask;
```

### reserved

Reserved for future use.

```cpp
char reserved[512];
```
