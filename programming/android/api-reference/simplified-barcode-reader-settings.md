---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader Android Edition
description: SimplifiedBarcodeReaderSettings class contains settings for barcode decoding. It is a sub-parameter of SimplifiedCaptureVisionSettings
keywords: SimplifiedBarcodeReaderSettings, SimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: SimplifiedBarcodeReaderSettings
permalink: /programming/android/api-reference/simplified-barcode-reader-settings.html
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` struct contains settings for barcode decoding. It is a sub-parameter of [`SimplifiedCaptureVisionSettings`]({{ site.dcv_android_api }}capture-vision-router/structs/simplified-capture-vision-settings.html)

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class SimplifiedBarcodeReaderSettings
```

## Attributes

| Attributes | Type | Description |
|------------|------|-------------|
| [`barcodeFormatIds`](#barcodeformatids) | *long* | Input a combined value of  `EnumBarcodeFormat` to specify the targeting barcode formats. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Set the expected barcode count. You can set it to 0 if the barcode count is unknown. |
| [`localizationModes`](#localizationmodes) | *EnumLocalizationMode[]* | Set the localization modes with an array of `EnumLocalizationMode`. |
| [`deblurModes`](#deblurmodes) | *EnumDeblurMode[]* | Set the deblur modes with an array of `EnumDeblurMode`. |
| [`minResultConfidence`](#minresultconfidence) | *int* | Set the minimum barcode result confidence to filter out the low confidence results. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* | Set the minimum barcode result text length. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *String* | Set a RegEx pattern for the barcode text. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | Set the max available threads for one task. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *GrayscaleTransformationMode[]* | Set the grayscale transformation mode with an array of `EnumGrayscaleTransformationMode`. It controls whether to decode  inverted barcodes. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *GrayscaleEnhancementMode[]* | Set the grayscale enhancement mode with an array of `EnumGrayscaleEnhancementModes`. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | Set the threshold for image shrinking. |

### barcodeFormatIds

Input a combined value of [`EnumBarcodeFormat`]({{site.dcv_enumerations}}barcode-reader/barcode-format.html?lang=android) to specify the targeted barcode formats.

```java
long barcodeFormatIds;
```

### expectedBarcodesCount

Set the expected barcode count. You can set it to 0 if the barcode count is unknown.

```java
int expectedBarcodesCount;
```

**Remarks**

* 0: detects at least one barcode.
* N ( N > 0 ): detects N barcodes.
* Dynamsoft Barcode Reader works in a loop trying different parameters to reach the number of expected barcodes specified by this parameter. If ExpectedBarcodesCount is 0, the loop stops after at least one barcode is found in an iteration. If ExpectedBarcodesCount is N, the loop stops once N barcodes are detected.

### localizationModes

Determines how to localize barcodes. The array consists of one or more modes, with each [EnumLocalizationMode]({{site.dcv_enumerations}}barcode-reader/localization-mode.html?lang=android) representing a different localization process.

```java
EnumLocalizationMode[] localizationModes;
```

**Remarks**

Some of the localization modes are specially optimized for certain barcode formats. For example, statistic marks for DPM barcodes and statistic postal code for postal code. If you want to further improve the read rate of certain barcodes, you can read the parameter reference of [LocalizationModes]({{site.dcv_parameters_reference}}barcode-reader-task-settings/localization-modes.html) for more information.

### deblurModes

Sets the priority for which deblurring algorithms the library will employ when dealing with blurry images. This array consists of [EnumDeblurMode]({{site.dcv_enumerations}}barcode-reader/deblur-mode.html?lang=android) items.

```java
EnumDeblurMode[] deblurModes;
```

### minResultConfidence

Set the minimum barcode result confidence to filter out low confidence results.

```java
int minResultConfidence;
```

**Remarks**

The default `minresultConfidence` value is 30.
### minBarcodeTextLength

Sets the minimum text length of the barcode results that the library will share. Any results that do not meet this text length will be discarded by the library.

```java
int minBarcodeTextLength;
```

### barcodeTextRegExPattern

Set a RegEx pattern for the barcode text. Any barcode results that don't follow this RegEx pattern will be discarded by the library.

```java
String barcodeTextRegExPattern;
```

### maxThreadsInOneTask

Set the maximum available threads for a single task.

```java
int maxThreadsInOneTask;
```

### grayscaleTransformationModes

Sets which grayscale transformation mode(s) the library will employ when reading barcodes. This parameter controls the library's ability to read inverted barcodes. The array consists of [GrayscaleTransformationMode]({{site.dcv_enumerations}}core/grayscale-transformation-mode.html?lang=android) items.

```java
EnumGrayscaleTransformationMode[] grayscaleTransformationModes;
```

**Remarks**

To learn more about reading inverted barcodes, please view [how to read inverted barcodes article]({{site.features}}read-inverted-barcodes.html?lang=android)

### grayscaleEnhancementModes

Sets which grayscale enhancement mode(s) the library will use when reading barcodes. The array consists of [GrayscaleEnhancementModes]({{site.dcv_enumerations}}core/grayscale-enhancement-mode.html?lang=objc,swift).

```java
EnumGrayscaleEnhancementMode[] grayscaleEnhancementModes;
```

**Remarks**

This parameter can be quite powerful if used properly. To learn more about this parameter and how it can be used, please see this page on how to [preprocess images]({{site.features}}preprocess-images.html?lang=android).

### scaleDownThreshold

Set the threshold for image shrinking when dealing with large images to help with the memory overhead. If both the width and height are larger then the threshold, the image is shrinked by half.

```java
int scaleDownThreshold;
```

**Remarks**

If you would like to learn more on how this parameter works, please see this page on how to [read barcodes from large images]({{site.features}}read-a-large-image.html?lang=android).
