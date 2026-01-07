---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader Android Edition
description: SimplifiedBarcodeReaderSettings class of Dynamsoft Barcode Reader Android contains settings for barcode decoding. It is a sub-parameter of SimplifiedCaptureVisionSettings
keywords: SimplifiedBarcodeReaderSettings, SimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: SimplifiedBarcodeReaderSettings
permalink: /programming/android/api-reference/simplified-barcode-reader-settings.html
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` class comes from the  [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_android_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html) class and contains settings specific to barcode decoding.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr

```java
class SimplifiedBarcodeReaderSettings
```

## Methods & Attributes

| Attributes | Type | Description |
|------------|------|-------------|
| [`barcodeFormatIds`](#barcodeformatids) | *long* | Defines a combined value of  `EnumBarcodeFormat` to specify which barcode format(s) the library should target. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Sets the expected barcode count. |
| [`localizationModes`](#localizationmodes) | *EnumLocalizationMode[]* | Defines the localization algorithm(s) used to localize barcodes. |
| [`deblurModes`](#deblurmodes) | *EnumDeblurMode[]* | Sets the priority for which deblurring algorithms the library will employ when dealing with blurry images. |
| [`minResultConfidence`](#minresultconfidence) | *int* | Sets the minimum barcode result confidence to filter out the low confidence results. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* | Sets the minimum barcode result text length. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *String* | Sets a RegEx pattern for the barcode text. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | Sets the max available threads for one task. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *GrayscaleTransformationMode[]* | Sets which grayscale transformation mode(s) the library will employ when reading barcodes. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *GrayscaleEnhancementMode[]* | Sets which grayscale enhancement mode(s) the library will use when reading barcodes. |
| [`scaleDownThreshold`](#scaledownthreshold) | *int* | Sets the threshold for image shrinking. |

| Methods | Description |
| [`toJson`](#tojson) | Generate a JSON string from this `SimplifiedBarcodeReaderSettings` object. |
| [`fromJson`](#fromjson) | Create a `SimplifiedBarcodeReaderSettings` object from a JSON string. |

### barcodeFormatIds

Defines a combined value of [`EnumBarcodeFormat`]({{site.dbr_android_api }}enum/barcode-format.html?lang=android) to specify which barcode format(s) the library should target.

```java
@EnumBarcodeFormat
long barcodeFormatIds;
```

### expectedBarcodesCount

Sets the expected barcode count. You can set it to 0 if the barcode count is unknown.

```java
@IntRange(from = 0)
int expectedBarcodesCount;
```

**Remarks**

* Set `expectedBarcodesCount` to 0 if the barcode count is unknown. The library will try to find at least 1 barcode.
* Set `expectedBarcodesCount` to 1 to reach the highest speed for processing single barcode.
* Set `expectedBarcodesCount` to "n" if there will be "n" barcodes to process from an image.
* Set `expectedBarcodesCount` to the highest expected value if there exists multiple barcodes but the exact count is not confirmed.

### localizationModes

Defines the localization algorithm(s) used to localize barcodes. The array consists of one or more modes, with each [EnumLocalizationMode]({{site.dbr_android_api }}enum/localization-mode.html?lang=android) representing a different localization process.

```java
@EnumLocalizationMode
int[] localizationModes;
```

**Remarks**

If you would like to learn more about the localization modes and how they work, please read the parameter reference of [LocalizationModes]({{site.dcvb_parameters_reference}}barcode-reader-task-settings/localization-modes.html) for more information.

### deblurModes

Sets the priority for which deblurring algorithms the library will employ when dealing with blurry images. This array consists of [`EnumDeblurMode`]({{site.dbr_android_api }}enum/deblur-mode.html?lang=android) items.

```java
@EnumDeblurMode
int[] deblurModes;
```

**Remarks**

If you would like to learn more about the deblur modes and how they work, please read the parameter reference of [DeblurModes]({{site.dcvb_parameters_reference}}barcode-reader-task-settings/deblur-modes.html) for more information.

### minResultConfidence

Set the minimum barcode result confidence to filter out results that do not meet the required level of confidence/accuracy. The higher the value of this parameter, the more accurate the results will be. If the library is struggling to find a barcode, lowering the value of this parameter can help.

```java
@IntRange(from = 0, to = 100)
int minResultConfidence;
```

**Remarks**

The default `minresultConfidence` value is 30. A typically accurate result that is returned by the library will be no less than 30, so that is why 30 is the default value for `minResultConfidence`.

### minBarcodeTextLength

Sets the minimum text length of the barcode results that the library will share. Any results that do not meet this text length will be discarded by the library.

```java
int minBarcodeTextLength;
```

### barcodeTextRegExPattern

Sets a RegEx pattern for the barcode text. Any barcode results that don't follow this RegEx pattern will be discarded by the library.

```java
String barcodeTextRegExPattern;
```

### maxThreadsInOneTask

Set the maximum available threads for a single task.

```java
int maxThreadsInOneTask;
```

### grayscaleTransformationModes

Sets which grayscale transformation mode(s) the library will employ when reading barcodes. This parameter controls the library's ability to read inverted barcodes. The array consists of [GrayscaleTransformationMode]({{site.dcvb_enumerations}}core/grayscale-transformation-mode.html?lang=android) items.

```java
int[] grayscaleTransformationModes;
```

**Remarks**

To learn more about reading inverted barcodes, please view this article on [how to read inverted barcodes]({{site.features}}read-inverted-barcodes.html?lang=android).

### grayscaleEnhancementModes

Sets which grayscale enhancement mode(s) the library will use when reading barcodes. The array consists of [GrayscaleEnhancementModes]({{site.dcvb_enumerations}}core/grayscale-enhancement-mode.html?lang=objc,swift).

```java
int[] grayscaleEnhancementModes;
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

### toJson

Generate a JSON string from this `SimplifiedBarcodeReaderSettings` object.

```java
String toJson()
```

**Return Value**

A JSON string that contains all the information of this object.

### fromJson

Create a `SimplifiedBarcodeReaderSettings` object from a JSON string.

```java
static SimplifiedBarcodeReaderSettings fromJson(String json);
```

**Parameters**

* `json`: A JSON string that contains all `SimplifiedBarcodeReaderSettings` required information.

**Return Value**

A `SimplifiedBarcodeReaderSettings` object.
