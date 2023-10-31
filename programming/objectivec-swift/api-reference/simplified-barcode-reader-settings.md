---
layout: default-layout
title: DSSimplifiedBarcodeReaderSettings Class - Dynamsoft Barcode Reader iOS Edition
description: DSSimplifiedBarcodeReaderSettings class contains settings for barcode decoding. It is a sub-parameter of DSSimplifiedCaptureVisionSettings
keywords: DSSimplifiedBarcodeReaderSettings, DSSimplifiedCaptureVisionSettings, inverted barcode, Deblur, localization, expected barcodes count, barcode format, confidence, RegEx pattern
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSSimplifiedBarcodeReaderSettings
permalink: /programming/objectivec-swift/api-reference/simplified-barcode-reader-settings.html
---

# DSSimplifiedBarcodeReaderSettings

The `DSSimplifiedBarcodeReaderSettings` struct contains settings for barcode decoding. It is a sub-parameter of [`DSSimplifiedCaptureVisionSettings`]({{ site.dcv_ios_api }}capture-vision-router/structs/simplified-capture-vision-settings.html).

## Definition

*Assembly:* DynamsoftBarcodeReader.xcframework

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
| [`barcodeFormatIds`](#barcodeformatids) | *DSBarcodeFormat* |Input a combined value of `BarcodeFormat` to specify the targeting barcode formats. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *NSInteger* | Set the expected barcode count. You can set it to 0 if the barcode count is unknown. |
| [`localizationModes`](#localizationmodes) | *NSArray* | Set the localization modes with an array of `DSLocalizationMode`. |
| [`deblurModes`](#deblurmodes) | *NSArray* | Set the deblur modes with an array of DSDeblurMode. |
| [`minResultConfidence`](#minresultconfidence) | *NSInteger* | Set the minimum barcode result confidence to filter out the low confidence results. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *NSInteger* | Set the minimum barcode result text length. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *NSString* | Set a RegEx pattern for the barcode text. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *NSInteger* | Set the max available threads for one task. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *NSArray* | Set the grayscale transformation mode with an array of [`DSGrayscaleTransformationMode`]({{ site.dcv_enumerations }}barcode-reader/grayscale-transformation-mode.html?lang=objc&swift). This parameter should be used when trying to decode inverted barcodes. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *NSArray* | Set the grayscale enhancement mode with an array of `DSGrayscaleEnhancementModes`. |
| [`scaleDownThreshold`](#scaledownthreshold) | *NSInteger* | Set the threshold for image shrinking. |

## barcodeFormatIds

Input a combined value of enumeration [BarcodeFormat]({{site.dcv_enumerations}}barcode-reader/barcode-format.html?lang=objc,swift) to specify the targeted barcode formats.

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

Set the expected barcode count. You can set it to 0 if the barcode count is unknown.

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
* 0: detects at least one barcode.
* N ( N > 0 ): detects N barcodes.
* Dynamsoft Barcode Reader works in a loop trying different parameters to reach the number of expected barcodes specified by this parameter. If ExpectedBarcodesCount is 0, the loop stops after at least one barcode is found in an iteration. If ExpectedBarcodesCount is N, the loop stops once N barcodes are detected.

## localizationModes

Determines how to localize barcodes. The array consists of one or more modes, with each [LocalizationMode]({{site.dcv_enumerations}}barcode-reader/localization-mode.html?lang=objc,swift) representing a different localization process.

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
var localizationModes: [DSLocalizationMode]? { get set }
```

**Remarks**

Different localization modes should be used depending on the targeted barcode formats - to learn more about this please see this [page]({{site.dcv_parameters_reference}}barcode-reader-task-settings/localization-modes.html).

## deblurModes

Sets the priority for which deblurring algorithms the library will employ when dealing with blurry images. This array consists of [DeblurMode]({{site.dcv_enumerations}}barcode-reader/deblur-mode.html?lang=objc,swift) items.

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
var deblurModes: [DSDeblurMode]? { get set }
```

## minResultConfidence

Set the minimum barcode result confidence to filter out low confidence results. This parameter helps the library return only the most accurate results.

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

The default `minresultConfidence` value is 30.

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

Set a RegEx pattern for the barcode text. Any barcode results that don't contain (fully or partially) this RegEx pattern will be discarded by the library.

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
@property(nonatomic, assign) NSInteger maxThreadsInOneTask;
```
2. 
```swift
var maxThreadsInOneTask: Int { get set }
```

## grayscaleTransformationModes

Sets which grayscale transformation mode(s) the library will employ when reading barcodes. This parameter controls the library's ability to read inverted barcodes. The array consists of [GrayscaleTransformationMode]({{site.dcv_enumerations}}core/grayscale-transformation-mode.html?lang=objc,swift) items.

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

To learn more about reading inverted barcodes, please see this [page]({{site.features}}read-inverted-barcodes.html?lang=objc,swift)

## grayscaleEnhancementModes

Sets which grayscale enhancement mode(s) the library will use when reading barcodes. The array consists of [GrayscaleEnhancementModes]({{site.dcv_enumerations}}core/grayscale-enhancement-mode.html?lang=objc,swift).

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