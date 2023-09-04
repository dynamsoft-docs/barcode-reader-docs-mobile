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
| [`barcodeFormatIds`](#barcodeformatids) | *long* | Input a combined value of  `EnumBarcodeFormat` to specify the targeting barcode formats.|
| [`expectedBarcodesCount`](#expectedbarcodescount) | *int* | Set the expected barcode count. You can set it to 0 if the barcode count is unknown.|
| [`localizationModes`](#localizationmodes) | *EnumLocalizationMode[]* | Set the localization modes with an array of `EnumLocalizationMode`.|
| [`deblurModes`](#deblurmodes) | *EnumDeblurMode[]* | Set the deblur modes with an array of `EnumDeblurMode`.|
| [`minResultConfidence`](#minresultconfidence) | *int* | Set the minimum barcode result confidence to filter out the low confidence results.|
| [`minBarcodeTextLength`](#minbarcodetextlength) | *int* | Set the minimum barcode result text length.|
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *String* | Set a RegEx pattern for the barcode text.|
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *int* | Set the max available threads for one task.|
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *GrayscaleTransformationMode[]* | Set the grayscale transformation mode with an array of `EnumGrayscaleTransformationMode`. It controls whether to decode the inverted barcodes.|
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *GrayscaleEnhancementMode[]* | Set the grayscale enhancement mode with an array of `EnumGrayscaleEnhancementModes`.|

### barcodeFormatIds

Input a combined value of `EnumBarcodeFormat` to specify the targeting barcode formats.

```java
long barcodeFormatIds
```

### expectedBarcodesCount

Set the expected barcode count. You can set it to 0 if the barcode count is unknown.

```java
int expectedBarcodesCount
```

### localizationModes

Set the localization modes with an array of `EnumLocalizationMode`.

```java
EnumLocalizationMode[] localizationModes
```

### deblurModes

Set the deblur modes with an array of EnumDeblurMode.

```java
EnumDeblurMode[] deblurModes
```

### minResultConfidence

Set the minimum barcode result confidence to filter out the low confidence results.

```java
int minResultConfidence
```

### minBarcodeTextLength

Set the minimum barcode result text length.

```java
int minBarcodeTextLength
```

### barcodeTextRegExPattern

Set a RegEx pattern for the barcode text.

```java
String barcodeTextRegExPattern
```

### maxThreadsInOneTask

Set the max available threads for one task.

```java
int maxThreadsInOneTask
```

### grayscaleTransformationModes

Set the grayscale transformation mode with an array of `EnumGrayscaleTransformationMode`. It controls whether to decode the inverted barcodes.

```java
EnumGrayscaleTransformationMode[] grayscaleTransformationModes
```

### grayscaleEnhancementModes

Set the grayscale enhancement mode with an array of `EnumGrayscaleEnhancementMode`.

```java
EnumGrayscaleEnhancementMode[] grayscaleEnhancementModes
```
