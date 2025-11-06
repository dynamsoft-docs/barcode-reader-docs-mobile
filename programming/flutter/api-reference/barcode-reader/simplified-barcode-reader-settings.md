---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Capture Vision Flutter Edition
description: SimplifiedBarcodeReaderSettings class contains settings for barcode decoding. It is a sub-parameter of SimplifiedCaptureVisionSettings
keywords: SimplifiedBarcodeReaderSettings, SimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern, flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: SimplifiedBarcodeReaderSettings
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` class comes from the [`SimplifiedCaptureVisionSettings`]({{ site.dcv_flutter_api }}capture-vision-router/simplified-capture-vision-settings.html) class and contains a limited subset of the parameters that influence the Barcode Reader's performance. If you would like to get familiar with the full parameters available to the Barcode Reader, please visit the [main parameters page]({{ site.dcvb_parameters }}file/index.html).

> [!TIP]
> If you visit the main parameters page, the majority of the settings related to the Barcode Reader will be in `BarcodeReaderTaskSetting`, `ImageParameter`, and `BarcodeFormatSpecification`. In order to use any of the settings that are not available in `SimplifiedBarcodeReaderSettings`, you will need to use a Capture Vision JSON template. Please see this [section](../../foundational-user-guide.md#using-a-json-template) of the user guide on how to use JSON templates.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class SimplifiedBarcodeReaderSettings
```

## Properties

| Property | Type | Description |
|----------|------|-------------|
| [`barcodeFormatIds`](#barcodeformatids) | [*EnumBarcodeFormat*](../enum/barcode-format.md) | Specifies which barcode format(s) the Barcode Reader will target. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Determines the expected barcode count, which can be set to 0 if the barcode count is unknown. |
| [`localizationModes`](#localizationmodes) | *List\<EnumLocalizationMode\>* | Defines which localization modes (as [`EnumLocalizationMode`](../enum/localization-mode.md)) the barcode reader will use during the detection process. |
| [`deblurModes`](#deblurmodes) | *List<EnumDeblurMode>* | Sets which deblur algorithms (as [`EnumDeblurMode`](../enum/deblur-mode.md)) the library will apply during the detection process when dealing with blurry images/frames. |
| [`minResultConfidence`](#minresultconfidence) | *int* | Specifies the minimum barcode result confidence to help filter out inaccurate results. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* | Sets the minimum barcode text length (in characters) for the barcode result to be considered valid. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *String* | Defines a regular expression pattern that the barcode text must match to be considered valid. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | Establishes the maximum number of threads available for a single detection task. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *List\<EnumGrayscaleTransformationMode\>* | Determines which grayscale transformation modes (as [`EnumGrayscaleTransformationMode`](../enum/grayscale-transformation-mode.md)) the barcode reader will apply before the detection process. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *List\<EnumGrayscaleEnhancementMode\>* | Sets which grayscale enhancement modes (as [`EnumGrayscaleEnhancementModes`](../enum/grayscale-enhancement-mode.md)) the library will apply before the detection process. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | Defines the threshold for scaling down the image/frame before processing to help with memory overhead. |

### barcodeFormatIds

Specifies which barcode format(s) (as [`EnumBarcodeFormat`](../enum/barcode-format.md)) the Barcode Reader will target. To learn more on how to set the barcode formats, please refer to the [Foundational Guide](../../foundational-user-guide.md#specify-barcode-formats-and-count). 

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

Defines which localization modes (as a list of [`EnumLocalizationMode`](../enum/localization-mode.md)) the barcode reader will use during the detection process. Each [`EnumLocalizationMode`](../enum/localization-mode.md)) represents a different localization method, some of which are more optimized for certain barcode formats over others.

```dart
List<EnumLocalizationMode> localizationModes;
```

**Remarks**

Certain localization modes are specially optimized for certain barcode formats. For example, `lines` is designed primarily for 1D and PDF417 barcodes, while `statisticsMarks` is optimized for DPM codes. If you want to further improve the read rate of certain barcode types, please go through the [`EnumLocalizationMode`](../enum/localization-mode.md) page to learn which modes to apply based on the targeted barcode format(s).

### deblurModes

Sets which deblur algorithms (as [`EnumDeblurMode`](../enum/deblur-mode.md)) the library will apply during the detection process when dealing with blurry images/frames.

```dart
List<EnumDeblurMode> deblurModes;
```

**Remarks**

If you would like to learn about the different modes in depth, please visit this [page]({{ site.dcvb_parameters }}reference/barcode-reader-task-settings/deblur-modes.html#candidate-modes-introduction). 

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

Determines which grayscale transformation modes (as [`EnumGrayscaleTransformationMode`](../enum/grayscale-transformation-mode.md)) the barcode reader will apply before the detection process. **This parameter controls the library's ability to read inverted barcodes.**

```dart
List<EnumGrayscaleTransformationMode> grayscaleTransformationModes;
```

**Remarks**

The order in which the transformations modes is set will determine the priority that the library will follow when searching for barcodes. Please see the table below for more info.

- [ .original ]: Process original coloured barcodes only.
- [ .inverted ]: Process inverted coloured barcodes only.
- [ .original, .inverted ]: Process both original and inverted coloured barcodes. The library will search for the original coloured barcodes first.
- [ .inverted, .original ]: Process both original and inverted coloured barcodes. The library will search for the inverted coloured barcodes first.

### grayscaleEnhancementModes

Sets which grayscale enhancement modes (as [`EnumGrayscaleEnhancementModes`](../enum/grayscale-enhancement-mode.md)) the library will apply before the detection process.

```dart
List<EnumGrayscaleEnhancementMode> grayscaleEnhancementModes;
```

**Remarks**

The grayscaleEnhancementModes are image processing methods that help enhance the quality of the grayscale image, which is an essential part of the detection process. By default, the library doesn't do any image preprocessing. Therefore, if your image has some distortion or is of lower quality, using the right image preprocessing methods can help produce a higher quality grayscale image and improve the readability of the image or frame.

To learn more about the different grayscale enhancement modes and what each of them does, please visit this [page]({{ site.dcvb_parameters }}reference/image-parameter/grayscale-enhancement-modes.html#candidate-modes-introduction).

### scaleDownThreshold

Defines the threshold for scaling down the image/frame before processing to help with memory overhead. If both the width and height are larger than the threshold, the image is shrunk by half.

```dart
int scaleDownThreshold;
```
