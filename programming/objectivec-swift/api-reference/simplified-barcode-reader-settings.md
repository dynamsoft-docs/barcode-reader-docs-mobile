---
layout: default-layout
title: DSSimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader iOS Edition
description: DSSimplifiedBarcodeReaderSettings class of Dynamsoft Barcode Reader iOS contains settings for barcode decoding. It is a sub-parameter of DSSimplifiedCaptureVisionSettings
keywords: DSSimplifiedBarcodeReaderSettings, DSSimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSSimplifiedBarcodeReaderSettings
permalink: /programming/objectivec-swift/api-reference/simplified-barcode-reader-settings.html
---

# DSSimplifiedBarcodeReaderSettings

The `DSSimplifiedBarcodeReaderSettings` class comes from the [`DSSimplifiedCaptureVisionSettings`]({{ site.dcvb_ios_api }}capture-vision-router/auxiliary-classes/simplified-capture-vision-settings.html) class and contains settings specific to barcode decoding.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NS_SWIFT_NAME(SimplifiedBarcodeReaderSettings)
@interface DSSimplifiedBarcodeReaderSettings : NSObject
```
2. 
```swift
class SimplifiedBarcodeReaderSettings : NSObject
```

## Attributes

| Attributes    | Type | Description |
| ------------- | ---- | ----------- |
| [`barcodeFormatIds`](#barcodeformatids) | *DSBarcodeFormat* | Defines a combined value of  `BarcodeFormat` to specify which barcode format(s) the library should target. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *NSInteger* | Sets the expected barcode count. |
| [`localizationModes`](#localizationmodes) | *NSArray* | Defines the localization algorithm(s) used to localize barcodes. |
| [`deblurModes`](#deblurmodes) | *NSArray* | Sets the priority for which deblurring algorithms the library will employ when dealing with blurry images. |
| [`minResultConfidence`](#minresultconfidence) | *NSInteger* | Sets the minimum barcode result confidence to filter out the low confidence results. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *NSInteger* | Sets the minimum barcode result text length. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *NSString* | Sets a RegEx pattern for the barcode text. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *NSInteger* | Sets the max available threads for one task. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *NSArray* | Sets which grayscale transformation mode(s) the library will employ when reading barcodes. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *NSArray* | Sets which grayscale enhancement mode(s) the library will use when reading barcodes. |
| [`scaleDownThreshold`](#scaledownthreshold) | *NSInteger* | Sets the threshold for image shrinking. |

## barcodeFormatIds

Defines a combined value of enumeration [`BarcodeFormat`]({{site.dcvb_enumerations}}barcode-reader/barcode-format.html?lang=objc,swift) to specify which barcode format(s) the library should target.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) DSBarcodeFormat barcodeFormatIds;
```
2. 
```swift
var barcodeFormatIds: DSBarcodeFormat { get set }
```

## expectedBarcodesCount

Sets the expected barcode count. You can set it to 0 if the barcode count is unknown.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) NSInteger expectedBarcodesCount;
```
2. 
```swift
var expectedBarcodesCount: Int { get set }
```

**Remarks**
* Set `expectedBarcodesCount` to 0 if the barcode count is unknown. The library will try to find at least 1 barcode.
* Set `expectedBarcodesCount` to 1 to reach the highest speed for processing single barcode.
* Set `expectedBarcodesCount` to "n" if there will be "n" barcodes to process from an image.
* Set `expectedBarcodesCount` to the highest expected value if there exists multiple barcodes but the exact count is not confirmed.

## localizationModes

Defines the localization algorithm(s) used to localize barcodes. The array consists of one or more modes, with each [LocalizationMode]({{site.dcvb_enumerations}}barcode-reader/localization-mode.html?lang=objc,swift) representing a different localization process.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, copy) NSArray *localizationModes;
```
2. 
```swift
var localizationModes: [LocalizationMode]? { get set }
```

**Remarks**

If you would like to learn more about the localization modes and how they work, please read the parameter reference of [LocalizationModes]({{site.dcvb_parameters_reference}}barcode-reader-task-settings/localization-modes.html) for more information.

## deblurModes

Sets the priority for which deblurring algorithms the library will employ when dealing with blurry images. This array consists of [`DeblurMode`]({{site.dcvb_enumerations}}barcode-reader/deblur-mode.html?lang=objc,swift) items.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, copy) NSArray *deblurModes;
```
2. 
```swift
var deblurModes: [DeblurMode]? { get set }
```

**Remarks**

If you would like to learn more about the deblur modes and how they work, please read the parameter reference of [DeblurModes]({{site.dcvb_parameters_reference}}barcode-reader-task-settings/deblur-modes.html) for more information.

## minResultConfidence

Set the minimum barcode result confidence to filter out results that do not meet the required level of confidence/accuracy. The higher the value of this parameter, the more accurate the results will be. If the library is struggling to find a barcode, lowering the value of this parameter can help.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) NSInteger minResultConfidence;
```
2. 
```swift
var minResultConfidence: Int { get set }
```

**Remarks**

The default `minresultConfidence` value is 30. A typically accurate result that is returned by the library will be no less than 30, so that is why 30 is the default value for `minResultConfidence`.

## minBarcodeTextLength

Sets the minimum text length of the barcode results that the library will share. Any results that do not meet this text length will be discarded by the library.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) NSInteger minBarcodeTextLength;
```
2. 
```swift
var minBarcodeTextLength: Int { get set }
```

## barcodeTextRegExPattern

Sets a RegEx pattern for the barcode text. Any barcode results that don't follow this RegEx pattern will be discarded by the library.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, copy) NSString *barcodeTextRegExPattern;
```
2. 
```swift
var barcodeTextRegExPattern: String? { get set }
```

## maxThreadsInOneTask

Set the maximum available threads for a single task.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) NSUInteger maxThreadsInOneTask;
```
2. 
```swift
var maxThreadsInOneTask: Int { get set }
```

## grayscaleTransformationModes

Sets which grayscale transformation mode(s) the library will employ when reading barcodes. This parameter controls the library's ability to read inverted barcodes. The array consists of [GrayscaleTransformationMode]({{site.dcvb_enumerations}}core/grayscale-transformation-mode.html?lang=objc,swift) items.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, copy) NSArray *grayscaleTransformationModes;
```
2. 
```swift
var grayscaleTransformationModes: [DSGrayscaleTransformationMode]? { get set }
```

**Remarks**

To learn more about reading inverted barcodes, please view this article on [how to read inverted barcodes]({{site.features}}read-inverted-barcodes.html?lang=objc,swift).

## grayscaleEnhancementModes

Sets which grayscale enhancement mode(s) the library will use when reading barcodes. The array consists of [GrayscaleEnhancementModes]({{site.dcvb_enumerations}}core/grayscale-enhancement-mode.html?lang=objc,swift).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, nullable, copy) NSArray *grayscaleEnhancementModes;
```
2. 
```swift
var grayscaleEnhancementModes: [DSGrayscaleEnhancementModes]? { get set }
```

**Remarks**

This parameter can be quite powerful if used properly. To learn more about this parameter and how it can be used, please see this page on how to [preprocess images]({{site.features}}preprocess-images.html?lang=objc,swift).

### scaleDownThreshold

Set the threshold for image shrinking when dealing with large images to help with the memory overhead. If both the width and height are larger then the threshold, the image is shrinked by half.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) NSInteger scaleDownThreshold;
```
2. 
```swift
var scaleDownThreshold: Int { get set }
```

**Remarks**

If you would like to learn more on how this parameter works, please see this page on how to [read barcodes from large images]({{site.features}}read-a-large-image.html?lang=objc,swift).
