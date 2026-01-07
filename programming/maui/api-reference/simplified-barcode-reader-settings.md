---
layout: default-layout
title: SimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader MAUI Edition
description: SimplifiedBarcodeReaderSettings class contains settings for barcode decoding. It is a sub-parameter of SimplifiedCaptureVisionSettings
keywords: SimplifiedBarcodeReaderSettings, SimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: SimplifiedBarcodeReaderSettings
---

# SimplifiedBarcodeReaderSettings

The `SimplifiedBarcodeReaderSettings` class comes from the [`SimplifiedCaptureVisionSettings`]({{ site.dcvb_maui_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html) class and contains settings specific to barcode decoding.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class SimplifiedBarcodeReaderSettings
```

## Properties

| Property | Type | Description |
|----------|------|-------------|
| [`BarcodeFormatIds`](#barcodeformatids) | *EnumBarcodeFormat* | Input a combined value of  `EnumBarcodeFormat` to specify the targeting barcode formats. |
| [`ExpectedBarcodesCount`](#expectedbarcodescount) | *int* | Set the expected barcode count. You can set it to 0 if the barcode count is unknown. |
| [`LocalizationModes`](#localizationmodes) | *EnumLocalizationMode[]* | Set the localization modes with an array of `EnumLocalizationMode`. |
| [`DeblurModes`](#deblurmodes) | *EnumDeblurMode[]* | Set the deblur modes with an array of `EnumDeblurMode`. |
| [`MinResultConfidence`](#minresultconfidence) | *int* | Set the minimum barcode result confidence to filter out the low confidence results. |
| [`MinBarcodeTextLength`](#minbarcodetextlength) | *int* | Set the minimum barcode result text length. |
| [`BarcodeTextRegExPattern`](#barcodetextregexpattern) | *String* | Set a RegEx pattern for the barcode text. |
| [`MaxThreadsInOneTask`](#maxthreadsinonetask) | *int* | Set the max available threads for one task. |
| [`GrayscaleTransformationModes`](#grayscaletransformationmodes) | *GrayscaleTransformationMode[]* | Set the grayscale transformation mode with an array of `EnumGrayscaleTransformationMode`. It controls whether to decode  inverted barcodes. |
| [`GrayscaleEnhancementModes`](#grayscaleenhancementmodes) | *GrayscaleEnhancementMode[]* | Set the grayscale enhancement mode with an array of `EnumGrayscaleEnhancementModes`. |
| [`ScaleDownThreshold`](#scaledownthreshold) | *int* | Set the threshold for image shrinking. |

### BarcodeFormatIds

Input a combined value of [`EnumBarcodeFormat`](enum/barcode-format.md) to specify the targeted barcode formats.

```csharp
EnumBarcodeFormat BarcodeFormatIds { get; set; }
```

### ExpectedBarcodesCount

Set the expected barcode count. You can set it to 0 if the barcode count is unknown.

```csharp
int ExpectedBarcodesCount { get; set; }
```

**Remarks**

- 0: detects at least one barcode.
- N ( N > 0 ): detects N barcodes.
- Dynamsoft Barcode Reader works in a loop trying different parameters to reach the number of expected barcodes specified by this parameter. If ExpectedBarcodesCount is 0, the loop stops after at least one barcode is found in an iteration. If ExpectedBarcodesCount is N, the loop stops once N barcodes are detected.

### LocalizationModes

Determines how to localize barcodes. The array consists of one or more modes, with each [EnumLocalizationMode](enum/localization-mode.md) representing a different localization process.

```csharp
EnumLocalizationMode[] LocalizationModes { get; set; }
```

**Remarks**

Some of the localization modes are specially optimized for certain barcode formats. For example, statistic marks for DPM barcodes and statistic postal code for postal code. If you want to further improve the read rate of certain barcodes, you can read the parameter reference of [LocalizationModes](enum/localization-mode.md) for more information.

### DeblurModes

Sets the priority for which deblurring algorithms the library will employ when dealing with blurry images. This array consists of [EnumDeblurMode](enum/deblur-mode.md) items.

```csharp
EnumDeblurMode[] DeblurModes { get; set; }
```

### MinResultConfidence

Set the minimum barcode result confidence to filter out low confidence results.

```csharp
int MinResultConfidence { get; set; }
```

**Remarks**

The default `minresultConfidence` value is 30.

### MinBarcodeTextLength

Sets the minimum text length of the barcode results that the library will share. Any results that do not meet this text length will be discarded by the library.

```csharp
int MinBarcodeTextLength { get; set; }
```

### BarcodeTextRegExPattern

Set a RegEx pattern for the barcode text. Any barcode results that don't follow this RegEx pattern will be discarded by the library.

```csharp
string BarcodeTextRegExPattern { get; set; }
```

### MaxThreadsInOneTask

Set the maximum available threads for a single task.

```csharp
int MaxThreadsInOneTask { get; set; }
```

### GrayscaleTransformationModes

Sets which grayscale transformation mode(s) the library will employ when reading barcodes. This parameter controls the library's ability to read inverted barcodes. The array consists of [GrayscaleTransformationMode]({{ site.dcvb_maui_api }}core/enum/grayscale-transformation-mode.html) items.

```csharp
EnumGrayscaleTransformationMode[] GrayscaleTransformationModes { get; set; }
```

**Remarks**

- [ GTM_ORIGINAL ]: Process the original coloured barcode only.
- [ GTM_INVERTED ]: Process the inverted coloured barcode only.
- [ GTM_ORIGINAL, GTM_INVERTED ]: Process both the original and inverted coloured barcode. The library will search for the original coloured barcode first.
- [ GTM_INVERTED, GTM_ORIGINAL ]: Process both the original and inverted coloured barcode. The library will search for the inverted coloured barcode first.

### GrayscaleEnhancementModes

Sets which grayscale enhancement mode(s) the library will use when reading barcodes. The array consists of [GrayscaleEnhancementModes]({{ site.dcvb_maui_api }}core/enum/grayscale-enhancement-mode.html) items.

```csharp
EnumGrayscaleEnhancementMode[] GrayscaleEnhancementModes { get; set; }
```

### ScaleDownThreshold

Set the threshold for image shrinking when dealing with large images to help with the memory overhead. If both the width and height are larger then the threshold, the image is shrinked by half.

```csharp
int ScaleDownThreshold { get; set; }
```
