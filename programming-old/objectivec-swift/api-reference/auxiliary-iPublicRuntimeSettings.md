---
layout: default-layout
title: iPublicRuntimeSettings Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iPublicRuntimeSettings Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iPublicRuntimeSettings, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iPublicRuntimeSettings.html
---

# Class iPublicRuntimeSettings

Defines a struct to configure the barcode reading runtime settings. These settings control the barcode recognition process such as which barcode types to decode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iPublicRuntimeSettings : NSObject
```
2. 
```swift
class iPublicRuntimeSettings : NSObject
```

| Attribute | Descriptions |
|---------- | ----------- |
| [`terminatePhase`](#terminatephase) | Sets the phase to stop the barcode reading algorithm. |
| [`timeout`](#timeout) | Set the maximum time spent on scanning one image (page). |
| [`maxAlgorithmThreadCount`](#maxalgorithmthreadcount) | Sets the number of threads the image processing algorithm will use to decode barcodes. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | Sets the number of barcodes expected to be detected for each image. |
| [`barcodeFormatIds`](#barcodeformatids) | BarcodeFormat group 1. Read more in [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) |
| [`barcodeFormatIds_2`](#barcodeformatids_2) | BarcodeFormat group 2. Read more in [`EnumBarcodeFormat_2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) |
| [`pdfRasterDPI`](#pdfrasterdpi) | Sets the output image resolution. |
| [`scaleDownThreshold`](#scaledownthreshold) | Sets the threshold for the image shrinking. |
| [`binarizationModes`](#binarizationmodes) | Sets the mode and priority for binarization. |
| [`localizationModes`](#localizationmodes) | Sets the mode and priority for localization algorithms. |
| [`furtherModes`](#furthermodes) | Further modes settings. Please read more in [`FurtherModes`](auxiliary-iFurtherModes.html) class. |
| [`deblurLevel`](#deblurlevel) | Sets the degree of blurriness of the barcode. |
| [`intermediateResultTypes`](#intermediateresulttypes) | Sets which types of intermediate result to be kept for further reference. |
| [`intermediateResultSavingMode`](#intermediateresultsavingmode) | Sets the mode for saving intermediate result. |
| [`resultCoordinateType`](#resultcoordinatetype) | Specifies the format for the coordinates returned. |
| [`textResultOrderModes`](#textresultordermodes) | Sets the mode and priority for the order of the text results returned. |
| [`returnBarcodeZoneClarity`](#returnbarcodezoneclarity) | Sets whether or not to return the clarity of the barcode zone. |
| [`region`](#region) | Sets the scan region. Please read more in [`iRegionDefinition`](auxiliary-iRegionDefinition.html) Class |
| [`minBarcodeTextLength`](#minbarcodetextlength) | Sets the range of barcode text length for barcodes search. |
| [`minResultConfidence`](#minresultconfidence) | The minimum confidence of the result. |
| [`scaleUpModes`](#scaleupmodes) | Sets the mode and priority to control the sampling methods of scale-up for linear barcode with small module sizes. |
| [`pdfReadingMode`](#pdfreadingmode) | Sets the way to detect barcodes from a PDF file when using the DecodeFile method. |
| [`deblurModes`](#deblurmodes) | Sets the mode and priority for deblurring. |
| [`barcodeZoneMinDistanceToImageBorders`](#barcodezonemindistancetoimageborders) | Sets the minimum distance (in pixels) between the barcode zone and image borders. |

## terminatePhase

Sets the phase to stop the barcode reading algorithm.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumTerminatePhase terminatePhase;
```
2. 
```swift
var terminatePhase: EnumTerminatePhase { get set }
```

**Value Range**

Any one of the [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) Enumeration items

**Default Value**

`EnumTerminatePhaseRecognized`

**Remarks**

When the recognition result is not desired, you can set this parameter can be set to skip certain processing stages.

**See Also**

[`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift)

## timeout

Sets the maximum amount of time (in milliseconds) that should be spent searching for a barcode per page. It does not include the time taken to load/decode an image (TIFF, PNG, etc.) from disk into memory.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger timeout;
```
2. 
```swift
var timeout: Int { get set }
```

**Value Range**

[0, 0x7fffffff]

**Default Value**

10000

**Remarks**

If you want to stop reading barcodes after a certain period of time, you can use this parameter to set a timeout.

## maxAlgorithmThreadCount

Sets the number of threads the image processing algorithm will use to decode barcodes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger maxAlgorithmThreadCount;
```
2. 
```swift
var maxAlgorithmThreadCount: Int { get set }
```

**Value Range**

[1, 4]

**Default Value**

4

**Remarks**

To keep a balance between speed and quality, the library concurrently runs four different threads for barcode decoding by default.

## expectedBarcodesCount

Sets the number of barcodes expected to be detected for each image.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger expectedBarcodesCount;
```
2. 
```swift
var expectedBarcodesCount: Int { get set }
```

**Value Range**

[0, 0x7fffffff]

**Default Value**

0

**Remarks**

0: means Unknown and it will find at least one barcode. 1: try to find one barcode. If one barcode is found, the library will stop the localization process and perform barcode decoding. n: try to find n barcodes. If the library only finds m (m<n) barcode, it will try different algorithms till n barcodes are found or all algorithms are tried.

## barcodeFormatIds

Sets the formats of the barcode in BarcodeFormat group 1 to be read. Barcode formats in BarcodeFormat group 1 can be combined.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger barcodeFormatIds;
```
2. 
```swift
var barcodeFormatIds: Int { get set }
```

**Value Range**

A combined value of [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) Enumeration items

**Default Value**

`EnumBarcodeFormatALL`

**Remarks**

If the barcode type(s) are certain, specifying the barcode type(s) to be read will speed up the recognition process. The barcode format our library will search for is composed of [BarcodeFormat group 1]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) and [BarcodeFormat group 2]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift), so you need to specify the barcode format in group 1 and group 2 individually.

When setting the parameter in *Swift*, please work with the rawValue of the enumeration as such

```swift
settings.barcodeFormatIds = EnumBarcodeFormat.ONED.rawValue;
```

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift), [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift)

## barcodeFormatIds_2

Sets the formats of the barcode in BarcodeFormat group 2 to be read. Barcode formats in BarcodeFormat group 2 can be combined.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger barcodeFormatIds_2;
```
2. 
```swift
var barcodeFormatIds_2: Int { get set }
```

**Value Range**

A combined value of [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) Enumeration items

**Default Value**

`EnumBarcodeFormat2NULL`

**Remarks**

If the barcode type(s) are certain, specifying the barcode type(s) to be read will speed up the recognition process. The barcode format our library will search for is composed of [BarcodeFormat group 1]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) and [BarcodeFormat group 2]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift), so you need to specify the barcode format in group 1 and group 2 individually.

When setting the parameter in *Swift*, please work with the rawValue of the enumeration as such

```swift
settings.barcodeFormatIds_2 = EnumBarcodeFormat2.POSTALCODE.rawValue;
```

**See Also**

[`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift), [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift)

## pdfRasterDPI

Sets the output image resolution.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger pdfRasterDPI;
```
2. 
```swift
var pdfRasterDPI: Int { get set }
```

**Value Range**

[100, 600]

**Default Value**

300

**Remarks**

When decoding barcodes from a PDF file using the DecodeFile method, the library will convert the PDF file to image(s) first, then perform barcode recognition.

## scaleDownThreshold

Sets the threshold for the image shrinking.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger scaleDownThreshold;
```
2. 
```swift
var scaleDownThreshold: Int { get set }
```

**Value Range**

[512, 0x7fffffff]

**Default Value**

2300

**Remarks**

If the shorter edge size is larger than the given threshold value, the library will calculate the required height and width of the barcode image and shrink the image to that size before localization. Otherwise, the library will perform barcode localization on the original image.

## binarizationModes

Sets the mode and priority for binarization.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readwrite, nullable) NSArray* binarizationModes;
```
2. 
```swift
var binarizationModes: [Any]? { get set }
```

**Value Range**

Each array item can be any one of the [`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift) Enumeration items.

**Default Value**

`[EnumBinarizationModeLocalBlock, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip, EnumBinarizationModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

[`EnumBinarizationMode`]({{ site.mobile_enum }}binarization-mode.html?lang=objc,swift)

## localizationModes

Sets the mode and priority for localization algorithms.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readwrite, nullable) NSArray* localizationModes;
```
2. 
```swift
var localizationModes: [Any]? { get set }
```

**Value Range**

Each array item can be any one of the [`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift) Enumeration items.

**Default Value**

`[EnumLocalizationModeConnectedBlocks, EnumLocalizationModeScanDirectly, EnumLocalizationModeStatistics, EnumLocalizationModeLines, EnumLocalizationModeSkip, EnumLocalizationModeSkip, EnumLocalizationModeSkip, EnumLocalizationModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

[`EnumLocalizationMode`]({{ site.mobile_enum }}localization-mode.html?lang=objc,swift)  

## furtherModes

Sets further modes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull) iFurtherModes furtherModes;
```
2. 
```swift
var furtherModes: iFurtherModes { get set }
```

## deblurLevel

Sets the degree of blurriness of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger deblurLevel;
```
2. 
```swift
var deblurLevel: Int { get set }
```

**Value Range**

[0, 9]

**Default Value**

9

**Remarks**

If you have a blurry image, you can set this property to a larger value. The higher the value set, the more effort the library will spend to decode images, but it may also slow down the recognition process.

## intermediateResultTypes

Sets which types of intermediate result to be kept for further reference. Intermediate result types can be combined.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger intermediateResultTypes;
```
2. 
```swift
var intermediateResultTypes: Int { get set }
```

**Value Range**

A combined value of [`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift) Enumeration items

**Default Value**

0

**See Also**

[`EnumIntermediateResultType`]({{ site.mobile_enum }}intermediate-result-type.html?lang=objc,swift)

## intermediateResultSavingMode

Sets the mode for saving intermediate result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumIntermediateResultSavingMode intermediateResultSavingMode;
```
2. 
```swift
var intermediateResultSavingMode: EnumIntermediateResultSavingMode { get set }
```

**Value Range**

A value of [`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=objc,swift) Enumeration items

**Default Value**

EnumIntermediateResultSavingModeMemory

**See Also**

[`EnumIntermediateResultSavingMode`]({{ site.mobile_enum }}intermediate-result-saving-mode.html?lang=objc,swift)

## resultCoordinateType

Specifies the format for the coordinates returned.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumResultCoordinateType resultCoordinateType;
```
2. 
```swift
var resultCoordinateType: EnumResultCoordinateType { get set }
```

**Value Range**

Any one of the [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) Enumeration items

**Default Value**

EnumResultCoordinateTypePixel

**See Also**

[`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift)

## textResultOrderModes

Sets the mode and priority for the order of the text results returned.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readwrite, nullable) NSArray* textResultOrderModes;
```
2. 
```swift
var textResultOrderModes: [Any]? { get set }
```

**Value Range**

Each array item can be any one of the [`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=objc,swift) Enumeration items.

**Default Value**

`[EnumTextResultOrderModeConfidence, EnumTextResultOrderModePosition, EnumTextResultOrderModeFormat, EnumTextResultOrderModeSkip, EnumTextResultOrderModeSkip, EnumTextResultOrderModeSkip, EnumTextResultOrderModeSkip, EnumTextResultOrderModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller the index, the higher the priority.

**See Also**

[`EnumTextResultOrderMode`]({{ site.mobile_enum }}text-result-order-mode.html?lang=objc,swift)

## returnBarcodeZoneClarity

Sets whether or not to return the clarity of the barcode zone.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger returnBarcodeZoneClarity;
```
2. 
```swift
var returnBarcodeZoneClarity: Int { get set }
```

**Value Range**

[0,1]

**Default Value**

0

**Remarks**

0: Do not return the clarity of the barcode zone; 1: Return the clarity of the barcode zone.  

## region

Sets the region definition including regionTop, regionLeft, regionRight, regionBottom, and regionMeasuredByPercentage.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nonnull) iRegionDefinition region;
```
2. 
```swift
var region: iRegionDefinition { get set }
```

## minBarcodeTextLength

Sets the range of barcode text length for barcodes search.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger minBarcodeTextLength;
```
2. 
```swift
var minBarcodeTextLength: Int { get set }
```

**Value Range**

[0, 0x7fffffff]

**Default Value**

0

**Remarks**

0: means no limitation on the barcode text length.

## minResultConfidence

The minimum confidence of the result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger minResultConfidence;
```
2. 
```swift
var minResultConfidence: Int { get set }
```

**Value Range**

[0, 100]

**Default Value**

0

**Remarks**

0: means no limitation on the result confidence.

## scaleUpModes

Sets the mode and priority to control the sampling methods of scale-up for linear barcode with small module sizes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readwrite, nullable) NSArray* scaleUpModes;
```
2. 
```swift
var scaleUpModes: [Any]? { get set }
```

**Value Range**

Each array item can be any one of the [`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=objc,swift) Enumeration items.

**Default Value**

`[EnumScaleUpModeAuto, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip, EnumScaleUpModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller the index, the higher the priority.

**See Also**

[`EnumScaleUpMode`]({{ site.mobile_enum }}scale-up-mode.html?lang=objc,swift)

## pdfReadingMode

Sets the way to detect barcodes from a PDF file when using the DecodeFile method.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumPDFReadingMode pdfReadingMode;
```
2. 
```swift
var pdfReadingMode: EnumPDFReadingMode { get set }
```

**Value Range**

Any one of the [`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=objc,swift) Enumeration items.

**Default Value**

`EnumPDFReadingModeAuto`  

**See Also**

[`EnumPDFReadingMode`]({{ site.mobile_enum }}pdf-reading-mode.html?lang=objc,swift)

## deblurModes

Sets the mode and priority for deblurring.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readwrite, nullable) NSArray* deblurModes;
```
2. 
```swift
var deblurModes: [Any]? { get set }
```

**Value Range**

Each array item can be any one of the [`EnumDeblurMode`]({{ site.mobile_enum }}deblur-mode.html?lang=objc,swift) Enumeration items.

**Default Value**

`[EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip, EnumDeblurModeSkip]`

**Remarks**

The array index represents the priority of the item. The smaller index is, the higher priority is.

**See Also**

[`EnumDeblurMode`]({{ site.mobile_enum }}deblur-mode.html?lang=objc,swift)

## barcodeZoneMinDistanceToImageBorders
Sets the minimum distance (in pixels) between the barcode zone and image borders.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger barcodeZoneMinDistanceToImageBorders;
```
2. 
```swift
var barcodeZoneMinDistanceToImageBorders: Int { get set }
```

**Value Range**

[0, 0x7fffffff]

**Default Value**

0

**Remarks**

0: means no limitation on the distance.
