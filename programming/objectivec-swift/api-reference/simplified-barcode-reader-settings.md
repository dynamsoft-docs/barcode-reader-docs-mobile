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

The `DSSimplifiedBarcodeReaderSettings` struct contains settings for barcode decoding. It is a sub-parameter of [`DSSimplifiedCaptureVisionSettings`]({{ site.dcv_ios_api }}capture-vision-router/structs/simplified-capture-vision-settings.html)

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

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
| [`barcodeFormatIds`](#barcodeformatids) | *DSBarcodeFormat* |Input a combined value of enumeration BarcodeFormat to specify the targeting barcode formats. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *NSInteger* | Set the expected barcode count. You can set it to 0 if the barcode count is unknown. |
| [`localizationModes`](#localizationmodes) | *NSArray* | Set the localization modes with an array of DSLocalizationMode. |
| [`deblurModes`](#deblurmodes) | *NSArray* | Set the deblur modes with an array of DSDeblurMode. |
| [`minResultConfidence`](#minresultconfidence) | *NSInteger* | Set the minimum barcode result confidence to filter out the low confidence results. |
| [`minBarcodeTextLength`](#minbarcodetextlength) | *NSInteger* | Set the minimum barcode result text length. |
| [`barcodeTextRegExPattern`](#barcodetextregexpattern) | *NSString* | Set a RegEx pattern for the barcode text. |
| [`maxThreadsInOneTask`](#maxthreadsinonetask) | *NSInteger* | Set the max available threads for one task. |
| [`grayscaleTransformationModes`](#grayscaletransformationmodes) | *NSArray* | Set the grayscale transformation mode with an array of DSGrayscaleTransformationMode. It controls whether to decode the inverted barcodes. |
| [`grayscaleEnhancementModes`](#grayscaleenhancementmodes) | *NSArray* | Set the grayscale enhancement mode with an array of DSGrayscaleEnhancementModes. |

## barcodeFormatIds

Input a combined value of enumeration BarcodeFormat to specify the targeting barcode formats.

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

## localizationModes

Set the localization modes with an array of DSLocalizationMode.

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

## deblurModes

Set the deblur modes with an array of DSDeblurMode.

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

Set the minimum barcode result confidence to filter out the low confidence results.

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

## minBarcodeTextLength

Set the minimum barcode result text length.

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

Set a RegEx pattern for the barcode text.

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

Set the max available threads for one task.

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

Set the grayscale transformation mode with an array of DSGrayscaleTransformationMode. It controls whether to decode the inverted barcodes.

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

## grayscaleEnhancementModes

Set the grayscale enhancement mode with an array of DSGrayscaleEnhancementModes.

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
