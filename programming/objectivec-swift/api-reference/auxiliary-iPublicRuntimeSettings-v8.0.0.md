---
layout: default-layout
title: iPublicRuntimeSettings Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iPublicRuntimeSettings Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iPublicRuntimeSettings, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iPublicRuntimeSettings-v8.0.0.html
---


# iPublicRuntimeSettings

Defines a struct to configure the barcode reading runtime settings. These settings control the barcode recognition process such as which barcode types to decode.

## Typedefs

```objc
@interface iPublicRuntimeSettings
```  
  
---

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`terminatePhase`](#terminatephase) | [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) |
| [`timeout`](#timeout) | *NSInteger* |
| [`maxAlgorithmThreadCount`](#maxalgorithmthreadcount) | *NSInteger* |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *NSInteger* |
| [`barcodeFormatIds`](#barcodeformatids) | *NSInteger* |
| [`barcodeFormatIds_2`](#barcodeformatids_2) | *NSInteger* |
| [`pdfRasterDPI`](#pdfrasterdpi) | *NSInteger* |
| [`scaleDownThreshold`](#scaledownthreshold) | *NSInteger* |
| [`binarizationModes`](#binarizationmodes) | *NSArray\**|
| [`localizationModes`](#localizationmodes) | *NSArray\**|
| [`furtherModes`](#furthermodes) | [`iFurtherModes`](auxiliary-iFurtherModes.html) |
| [`deblurLevel`](#deblurlevel) | *NSInteger* |
| [`intermediateResultTypes`](#intermediateresulttypes) | *NSInteger* |
| [`intermediateResultSavingMode`](#intermediateresultsavingmode) | [`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=objc,swift) |
| [`resultCoordinateType`](#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) |
| [`textResultOrderModes`](#textresultordermodes) | *NSArray\**|
| [`returnBarcodeZoneClarity`](#returnbarcodezoneclarity) | *NSInteger* |
| [`region`](#region) | [`iRegionDefinition`](auxiliary-iRegionDefinition.html) |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *NSInteger* |
| [`minResultConfidence`](#minresultconfidence) | *NSInteger* |
| [`scaleUpModes`](#scaleupmodes) | *NSArray\**|
| [`pdfReadingMode`](#pdfreadingmode) | [`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=objc,swift) | 
| [`deblurModes`](#deblurmodes) | *NSArray\**|

### terminatePhase

Sets the phase to stop the barcode reading algorithm.

```objc
EnumTerminatePhase terminatePhase
```

**Value range**

Any one of the [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) Enumeration items

**Default value**

`EnumTerminatePhaseRecognized`

**Remarks**

When the recognition result is not desired, you can set this parameter can be set to skip certain processing stages.

**See also**

[`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift)

### timeout

Sets the maximum amount of time (in milliseconds) that should be spent searching for a barcode per page. It does not include the time taken to load/decode an image (TIFF, PNG, etc.) from disk into memory.

```objc
NSInteger timeout
```

**Value range**

[0, 0x7fffffff]

**Default value**

10000

**Remarks**

If you want to stop reading barcodes after a certain period of time, you can use this parameter to set a timeout.

### maxAlgorithmThreadCount

Sets the number of threads the image processing algorithm will use to decode barcodes.

```objc
NSInteger timeout
```

**Value range**

[1, 4]

**Default value**

4

**Remarks**
    To keep a balance between speed and quality, the library concurrently runs four different threads for barcode decoding by default.

### expectedBarcodesCount

Sets the number of barcodes expected to be detected for each image.

```objc
NSInteger expectedBarcodesCount
```

**Value range**

[0, 0x7fffffff]

**Default value**

0

**Remarks**

0: means Unknown and it will find at least one barcode. 1: try to find one barcode. If one barcode is found, the library will stop the localization process and perform barcode decoding. n: try to find n barcodes. If the library only finds m (m<n) barcode, it will try different algorithms till n barcodes are found or all algorithms are tried.

### barcodeFormatIds

Sets the formats of the barcode in BarcodeFormat group 1 to be read. Barcode formats in BarcodeFormat group 1 can be combined.

```objc
NSInteger barcodeFormatIds
```

**Value range**

A combined value of [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) Enumeration items

**Default value**

`EnumBarcodeFormatALL`

**Remarks**

If the barcode type(s) are certain, specifying the barcode type(s) to be read will speed up the recognition process. The barcode format our library will search for is composed of [BarcodeFormat group 1]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) and [BarcodeFormat group 2]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift), so you need to specify the barcode format in group 1 and group 2 individually.

**See also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift), [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift)

### barcodeFormatIds_2

Sets the formats of the barcode in BarcodeFormat group 2 to be read. Barcode formats in BarcodeFormat group 2 can be combined.

```objc
NSInteger barcodeFormatIds_2
```

**Value range**

A combined value of [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) Enumeration items

**Default value**

`EnumBarcodeFormat2NULL`

**Remarks**

If the barcode type(s) are certain, specifying the barcode type(s) to be read will speed up the recognition process. The barcode format our library will search for is composed of [BarcodeFormat group 1]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) and [BarcodeFormat group 2]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift), so you need to specify the barcode format in group 1 and group 2 individually.

**See also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift), [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift)

### pdfRasterDPI

Sets the output image resolution.

```objc
NSInteger pdfRasterDPI
```

**Value range**

[100, 600]

**Default value**

300

**Remarks**
    When decoding barcodes from a PDF file using the DecodeFile method, the library will convert the PDF file to image(s) first, then perform barcode recognition.

### scaleDownThreshold

Sets the threshold for the image shrinking.

```objc
NSInteger scaleDownThreshold
```

**Value range**
    [512, 0x7fffffff]

**Default value**
    2300

**Remarks**
    If the shorter edge size is larger than the given threshold value, the library will calculate the required height and width of the barcode image and shrink the image to that size before localization. Otherwise, the library will perform barcode localization on the original image.

### binarizationModes

Sets the mode and priority for binarization.

```objc
NSArray* binarizationModes[8]
```

**Value range**

Each array item can be any one of the [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) Enumeration items.

**Default value**

`[EnumBinarizationModeLocalBlock, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See also**

[`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift)

### localizationModes

Sets the mode and priority for localization algorithms.

```objc
NSArray* localizationModes[8]
```

**Value range**

Each array item can be any one of the [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) Enumeration items.

**Default value**

`[EnumLocalizationModeConnectedBlocks, EnumLocalizationModeScanDirectly, EnumLocalizationModeStatistics, EnumLocalizationModeLines, EnumLocalizationModeSkip, EnumLocalizationModeSkip, EnumLocalizationModeSkip, EnumLocalizationModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See also**

[`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift)

### furtherModes

Sets further modes.

```objc
iFurtherModes furtherModes
```

### deblurLevel

Sets the degree of blurriness of the barcode.

```objc
NSInteger deblurLevel
```

**Value range**

[0, 9]

**Default value**

9

**Remarks**

If you have a blurry image, you can set this property to a larger value. The higher the value set, the more effort the library will spend to decode images, but it may also slow down the recognition process.

### intermediateResultTypes

Sets which types of intermediate result to be kept for further reference. Intermediate result types can be combined.

```objc
NSInteger intermediateResultTypes
```

**Value range**

A combined value of [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift) Enumeration items

**Default value**

0

**See also**
    [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift)

### intermediateResultSavingMode

Sets the mode for saving intermediate result.

```objc
EnumIntermediateResultSavingMode intermediateResultSavingMode
```

**Value range**

A value of [`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=objc,swift) Enumeration items

**Default value**

EnumIntermediateResultSavingModeMemory

**See also**

[`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=objc,swift)

### resultCoordinateType

Specifies the format for the coordinates returned.

```objc
EnumResultCoordinateType resultCoordinateType
```

**Value range**

Any one of the [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) Enumeration items

**Default value**

EnumResultCoordinateTypePixel

**See also**

[`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift)

### textResultOrderModes

Sets the mode and priority for the order of the text results returned.

```objc
NSArray* textResultOrderModes[8]
```

**Value range**

Each array item can be any one of the [`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=objc,swift) Enumeration items.

**Default value**

`[EnumTextResultOrderModeConfidence, EnumTextResultOrderModePosition, EnumTextResultOrderModeFormat, EnumTextResultOrderModeSkip, EnumTextResultOrderModeSkip, EnumTextResultOrderModeSkip, EnumTextResultOrderModeSkip, EnumTextResultOrderModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller the index, the higher the priority.

**See also**

[`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=objc,swift)

### returnBarcodeZoneClarity

Sets whether or not to return the clarity of the barcode zone.

```objc
NSInteger returnBarcodeZoneClarity
```

**Value range**

[0,1]

**Default value**

0

**Remarks**

0: Do not return the clarity of the barcode zone; 1: Return the clarity of the barcode zone.  

### region

Sets the region definition including regionTop, regionLeft, regionRight, regionBottom, and regionMeasuredByPercentage.

```objc
iRegionDefinition region
```

### minBarcodeTextLength

Sets the range of barcode text length for barcodes search.

```objc
NSInteger minBarcodeTextLength
```

**Value range**

[0, 0x7fffffff]

**Default value**

0

**Remarks**

0: means no limitation on the barcode text length.

### minResultConfidence

The minimum confidence of the result.

```objc
NSInteger minResultConfidence
```

**Value range**

[0, 100]

**Default value**

0

**Remarks**

0: means no limitation on the result confidence.

### scaleUpModes

Sets the mode and priority to control the sampling methods of scale-up for linear barcode with small module sizes.

```objc
NSArray* scaleUpModes[8]
```

**Value range**

Each array item can be any one of the [`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=objc,swift) Enumeration items.

**Default value**

`[EnumScaleUpModeAuto, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller the index, the higher the priority.

**See also**

[`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=objc,swift)

### pdfReadingMode

Sets the way to detect barcodes from a PDF file when using the DecodeFile method.

```objc
EnumPDFReadingMode pdfReadingMode
```

**Value range**

Any one of the [`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=objc,swift) Enumeration items.

**Default value**

`EnumPDFReadingModeAuto`  

**See also**

[`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=objc,swift)

### deblurModes

Sets the mode and priority for deblurring.

```objc
NSArray* deblurModes[10]
```

**Value range**

Each array item can be any one of the [`EnumDeblurMode`]({{ site.mobile_enum }}deblur-mode.html?lang=objc,swift) Enumeration items.

**Default value**

`[EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See also**

[`EnumDeblurMode`]({{ site.mobile_enum }}deblur-mode.html?lang=objc,swift)
