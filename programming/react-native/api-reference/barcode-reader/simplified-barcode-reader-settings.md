---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Capture Vision React Native Edition
description: SimplifiedBarcodeReaderSettings class contains settings for barcode decoding. It is a sub-parameter of SimplifiedCaptureVisionSettings
keywords: SimplifiedBarcodeReaderSettings, SimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern, flutter
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: SimplifiedBarcodeReaderSettings
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` class comes from the [`SimplifiedCaptureVisionSettings`]({{ site.dcv_react_native_api }}capture-vision-router/simplified-capture-vision-settings.html) class and contains a limited subset of the parameters that influence the Barcode Reader's performance. If you would like to get familiar with the full parameters available to the Barcode Reader, please visit the [main parameters page]({{ site.dcvb_parameters }}file/index.html).

> [!TIP]
> If you visit the main parameters page, the majority of the settings related to the Barcode Reader will be in `BarcodeReaderTaskSetting`, `ImageParameter`, and `BarcodeFormatSpecification`. In order to use any of the settings that are not available in `SimplifiedBarcodeReaderSettings`, you will need to use a Capture Vision JSON template. Please see this [section](../../foundational-user-guide.md#using-a-json-template) of the user guide on how to use JSON templates.

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
class SimplifiedBarcodeReaderSettings
```

## Properties

| Property | Type | Description |
|----------|------|-------------|
| [`barcodeFormatIds`](#barcodeformatids) | [*EnumBarcodeFormat*]({{ site.dcv_react_native_api }}core/enum/barcode-format.html) | Specifies which barcode format(s) the Barcode Reader will target. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *number* | Determines the expected barcode count, which can be set to 0 if the barcode count is unknown. |
| [`localizationModes`](#localizationmodes) | *Array\<EnumLocalizationMode\>* | Defines which localization modes (as [`EnumLocalizationMode`]({{ site.dcv_react_native_api }}core/enum/localization-mode.html)) the barcode reader will use during the detection process. |
| [`deblurModes`](#deblurmodes) | *Array\<EnumDeblurMode\>* | Sets which deblur algorithms (as [`EnumDeblurMode`]({{ site.dcv_react_native_api }}core/enum/deblur-mode.html)) the library will apply during the detection process when dealing with blurry images/frames. |
| [`minResultConfidence`](#minresultconfidence) | *number* | Specifies the minimum barcode result confidence to help filter out inaccurate results. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *number* | Sets the minimum barcode text length (in characters) for the barcode result to be considered valid. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *string* | Defines a regular expression pattern that the barcode text must match to be considered valid. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *number* | Establishes the maximum number of threads available for a single detection task. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *Array\<EnumGrayscaleTransformationMode\>* | Determines which grayscale transformation modes (as [`EnumGrayscaleTransformationMode`]({{ site.dcv_react_native_api }}core/enum/grayscale-transformation-mode.html)) the barcode reader will apply before the detection process. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *Array\<EnumGrayscaleTransformationMode\>* | Sets which grayscale enhancement modes (as [`EnumGrayscaleEnhancementModes`]({{ site.dcv_react_native_api }}core/enum/grayscale-enhancement-mode.html)) the library will apply before the detection process. |
| [`scaleDownThreshold`](#scaledownthreshold) | *number* | Defines the threshold for scaling down the image/frame before processing to help with memory overhead. |

### barcodeFormatIds

Specifies which barcode format(s) (as [`EnumBarcodeFormat`]({{ site.dcv_react_native_api }}core/enum/barcode-format.html)) the Barcode Reader will target. To learn more on how to set the barcode formats, please refer to the [Foundational Guide](../../foundational-user-guide.md#specify-barcode-formats-and-count). 

```js
barcodeFormatIds?: EnumBarcodeFormat | bigint;
```

### expectedBarcodesCount

Determines the expected barcode count, which can be set to 0 if the barcode count is unknown.

```js
expectedBarcodesCount?: number;
```

**Remarks**

- Set `expectedBarcodesCount` to 0 if the barcode count is unknown. The library will try to find at least 1 barcode.
- Set `expectedBarcodesCount` to 1 to reach the highest speed for processing single barcode.
- Set `expectedBarcodesCount` to "n" if there will be "n" barcodes to process from an image.
- Set `expectedBarcodesCount` to the highest expected value if there exists multiple barcodes but the exact count is not confirmed.

### localizationModes

Determines how to localize the barcodes.

- View more information about [LocalizationMode Parameters]({{ site.dcvb_parameters }}reference/barcode-reader-task-settings/localization-modes.html).
- View the available [`EnumLocalizationMode`]({{ site.dcv_react_native_api }}core/enum/localization-mode.html) members.

```js
localizationModes?: Array<EnumLocalizationMode> | Int32Array;
```

### deblurModes

Determines which deblur algorithms to apply when decoding the barcodes.

- View more information about [DeblurMode Parameters]({{ site.dcvb_parameters }}reference/barcode-reader-task-settings/deblur-modes.html).
- View the available [`EnumDeblurMode`]({{ site.dcv_react_native_api }}core/enum/deblur-mode.html) members.

```js
deblurModes?: Array<EnumDeblurMode> | Int32Array;
```

### minResultConfidence

Specifies the minimum barcode result confidence to help filter out low-confidence results.

```js
minResultConfidence?: number;
```

**Remarks**

The default `minResultConfidence` value is 30.

### minBarcodeTextLength

Sets the minimum barcode text length to filter out non-target barcodes.

```js
minBarcodeTextLength?: number;
```

### barcodeTextRegExPattern

Defines a regular expression pattern to filter out non-target barcodes.

```js
barcodeTextRegExPattern?: string;
```

### maxThreadsInOneTask

Set the maximum available threads count in one barcode decoding task.

```js
maxThreadsInOneTask?: number;
```

### grayscaleTransformationModes

Determines whether to decode inverted barcodes.

- View more information about [GrayscaleTransformationMode Parameter]({{ site.dcvb_parameters }}reference/image-parameter/grayscale-transformation-modes.html).
- View the available [`EnumGrayscaleTransformationMode`]({{ site.dcv_react_native_api }}core/enum/grayscale-transformation-mode.html) members.

```js
grayscaleTransformationModes?: Array<EnumGrayscaleTransformationMode> | Int32Array;
```

### grayscaleEnhancementModes

Determines how to enhance the quality of the grayscale image.

- View more information about [GrayscaleEnhancementMode Parameter]({{ site.dcvb_parameters }}reference/image-parameter/grayscale-enhancement-modes.html).
- View the available [`EnumGrayscaleEnhancementMode`]({{ site.dcv_react_native_api }}core/enum/grayscale-enhancement-mode.html) members.

```js
grayscaleEnhancementModes?: Array<EnumGrayscaleEnhancementMode> | Int32Array;
```

### scaleDownThreshold

Defines the threshold for scaling down the image/frame before processing to help with memory overhead. If both the width and height are larger than the threshold, the image is shrunk by half.

```js
scaleDownThreshold?: number;
```
