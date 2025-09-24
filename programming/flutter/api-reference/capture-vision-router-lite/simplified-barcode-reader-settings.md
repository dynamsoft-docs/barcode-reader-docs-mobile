---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader Flutter Edition
description: SimplifiedBarcodeReaderSettings class contains settings for barcode decoding. It is a sub-parameter of SimplifiedCaptureVisionSettings
keywords: SimplifiedBarcodeReaderSettings, SimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern, flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: SimplifiedBarcodeReaderSettings
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` class comes from the [`SimplifiedCaptureVisionSettings`](./capture-vision-router-lite/simplified-capture-vision-settings.md) class and contains a limited subset of the parameters that influence the Barcode Reader's performance. If you would like to get familiar with the full parameters available to the Barcode Reader, please visit the [main parameters page]({{ site.dcvb_parameters }}file/index.html?product=dbr&lang=objectivec-swift).

> [!TIP]
> If you visit the main parameters page, the majority of the settings related to the Barcode Reader will be in `BarcodeReaderTaskSetting`, `ImageParameter`, and `BarcodeFormatSpecification`.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class SimplifiedBarcodeReaderSettings
```

## Properties

| Property | Type | Description |
|----------|------|-------------|
| [`barcodeFormatIds`](#barcodeformatids) | [*EnumBarcodeFormat*](./enum/barcode-format.md) | Specifies which barcode format(s) the Barcode Reader will target. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Determines the expected barcode count, which can be set to 0 if the barcode count is unknown. |
| [`localizationModes`](#localizationmodes) | *List<EnumLocalizationMode>* | Defines which localization modes (as [`EnumLocalizationMode`](./enum/localization-mode.md)) the barcode reader will use during the detection process. |
| [`deblurModes`](#deblurmodes) | *List<EnumDeblurMode>* | Sets which deblur algorithms (as [`EnumDeblurMode`](./enum/deblur-mode.md)) the library will apply during the detection process when dealing with blurry images/frames. |
| [`minResultConfidence`](#minresultconfidence) | *int* | Specifies the minimum barcode result confidence to help filter out inaccurate results. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* | Sets the minimum barcode text length (in characters) for the barcode result to be considered valid. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *String* | Defines a regular expression pattern that the barcode text must match to be considered valid. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | Establishes the maximum number of threads available for a single detection task. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *List<EnumGrayscaleTransformationMode>* | Determines which grayscale transformation modes (as [`EnumGrayscaleTransformationMode`](./enum/grayscale-transformation-mode.md)) the barcode reader will apply before the detection process. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *List<EnumGrayscaleEnhancementMode>* | Sets which grayscale enhancement modes (as [`EnumGrayscaleEnhancementModes`](./enum/grayscale-enhancement-mode.md)) the library will apply before the detection process. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | Defines the threshold for scaling down the image/frame before processing to help with memory overhead. |

### barcodeFormatIds

Specifies which barcode format(s) (as [EnumBarcodeFormat](./enum/barcode-format.md)) the Barcode Reader will target. To learn more on how to set the barcode formats, please refer to the [Foundational Guide](../foundational-user-guide.md#specify-barcode-formats-and-count). 

```dart
EnumBarcodeFormat barcodeFormatIds;
```

### expectedBarcodesCount

Determines the expected barcode count, which can be set to 0 if the barcode count is unknown.

```dart
int expectedBarcodesCount;
```

**Remarks**

- 0: detects at least one barcode.
- N ( N > 0 ): detects N barcodes.
- Dynamsoft Barcode Reader works in a loop trying different parameters to reach the number of expected barcodes specified by this parameter. If ExpectedBarcodesCount is 0, the loop stops after at least one barcode is found in an iteration. If ExpectedBarcodesCount is N, the loop stops once N barcodes are detected.

### localizationModes

Defines which localization modes (as a list of [`EnumLocalizationMode`](./enum/localization-mode.md)) the barcode reader will use during the detection process. Each [`EnumLocalizationMode`](./enum/localization-mode.md)) represents a different localization method, some of which are more optimized for certain barcode formats over others.

```dart
List<EnumLocalizationMode> localizationModes;
```

**Remarks**

Certain localization modes are specially optimized for certain barcode formats. For example, `lines` is designed primarily for 1D and PDF417 barcodes, while `statisticsMarks` is optimized for DPM codes. If you want to further improve the read rate of certain barcode types, please go through [EnumLocalizationMode](enum/localization-mode.md) page to learn which modes to apply based on the targeted barcode format(s).

### deblurModes

Sets which deblur algorithms (as [`EnumDeblurMode`](./enum/deblur-mode.md)) the library will apply during the detection process when dealing with blurry images/frames.

```dart
List<EnumDeblurMode> deblurModes;
```

### minResultConfidence

Specifies the minimum barcode result confidence to help filter out inaccurate results. Confidence is a measure of a barcode result's accuracy, so by setting this parameter to a higher value, you ensure that the library will relay only the more accurate results.

```dart
int minResultConfidence;
```

**Remarks**

The default `minresultConfidence` value is 30, which is a sufficient level of accuracy for most scenarios.

### minBarcodeTextLength

Sets the minimum barcode text length (in characters) for the barcode result to be considered valid. Any results that do not meet this text length will be discarded by the library.

```dart
int minBarcodeTextLength;
```

### barcodeTextRegExPattern

Defines a regular expression pattern that the barcode text must match to be considered valid. Any barcode results that do not follow this RegEx pattern will be discarded by the library.

```dart
String barcodeTextRegExPattern;
```

### maxThreadsInOneTask

Establishes the maximum number of threads available for a single detection task.

```dart
int maxThreadsInOneTask;
```

### grayscaleTransformationModes

Determines which grayscale transformation modes (as [`EnumGrayscaleTransformationMode`](./enum/grayscale-transformation-mode.md)) the barcode reader will apply before the detection process. *This parameter controls the library's ability to read inverted barcodes.*

```dart
List<EnumGrayscaleTransformationMode> grayscaleTransformationModes;
```

**Remarks**

- [ GTM_ORIGINAL ]: Process original coloured barcodes only.
- [ GTM_INVERTED ]: Process inverted coloured barcodes only.
- [ GTM_ORIGINAL, GTM_INVERTED ]: Process both original and inverted coloured barcodes. The library will search for the original coloured barcodes first.
- [ GTM_INVERTED, GTM_ORIGINAL ]: Process both original and inverted coloured barcodes. The library will search for the inverted coloured barcodes first.

### grayscaleEnhancementModes

Sets which grayscale enhancement modes (as [`EnumGrayscaleEnhancementModes`](./enum/grayscale-enhancement-mode.md)) the library will apply before the detection process.

```dart
List<EnumGrayscaleEnhancementMode> grayscaleEnhancementModes;
```

Remarks



### scaleDownThreshold

Defines the threshold for scaling down the image/frame before processing to help with memory overhead. If both the width and height are larger than the threshold, the image is shrinked by half.

```dart
int scaleDownThreshold;
```
