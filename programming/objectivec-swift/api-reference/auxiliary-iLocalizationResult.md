---
layout: default-layout
title: iLocalizationResult Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iLocalizationResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iLocalizationResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iLocalizationResult.html
---


# Class iLocalizationResult

The `iLocalizationResult` extends the class [`iTextResult`](auxiliary-iTextResult.md) and [`iIntermediateResult`](auxiliary-iIntermediateResult.md). It stores the barcode localization data.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iLocalizationResult : NSObject
```
2. 
```swift
class iLocalizationResult : NSObject
```

| Attribute | Type | Description |
|---------- | ---- | ----------- |
| [`terminatePhase`](#terminatephase) | [`EnumTerminatePhase`]({{ site.mobile_enum }}terminate-phase.html?lang=objc,swift) | The terminate phase of localization result. |
| [`barcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](#barcodeformat_2 ) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](#barcodeformatstring) | *NSString \** | Barcode type as string. |
| [`resultPoints`](#resultpoints) | *NSArray \** | The vertices coordinates information of the barcode region. |
| [`angle`](#angle) | *NSInteger* | The angle of a barcode. Values range is from 0 to 360. |
| [`moduleSize`](#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`pageNumber`](#pagenumber) | *NSInteger* | The page number the barcode located in. The index is 0-based. |
| [`regionName`](#regionname) | *NSString \** | The region name the barcode located in. |
| [`documentName`](#documentname)| *NSString \** | The document name. |
| [`resultCoordinateType`](#resultcoordinatetype) | [`EnumResultCoordinateType`]({{ site.mobile_enum }}result-coordinate-type.html?lang=objc,swift) | The coordinate type. |
| [`accompanyingTextBytes`](#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`confidence`](#confidence) | *NSInteger* | The confidence of the localization result. |
| [`transformationMatrix`](#transformationmatrix) | *CGAffineTransform* | A transformation matrix that can transform the coordinates of the `resultPoints`. The transformationMatrix is calculated from the orientation information of the image. |

## terminatePhase

The terminate phase of localization result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumTerminatePhase terminatePhase
```
2. 
```swift
var terminatePhase: EnumTerminatePhase { get set }
```

## barcodeFormat

Barcode type in BarcodeFormat group 1.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumBarcodeFormat barcodeFormat
```
2. 
```swift
var barcodeFormat: EnumBarcodeFormat { get set }
```

## barcodeFormat_2

Barcode type in BarcodeFormat group 2.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumBarcodeFormat2 barcodeFormat_2
```
2. 
```swift
var barcodeFormat_2: EnumBarcodeFormat2 { get set }
```

## barcodeFormatString

Barcode type as string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSString* barcodeFormatString
```
2. 
```swift
var barcodeFormatString: String? { get set }
```

## resultPoints

The resultPoints are Four CGPoints that localize the result area.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSArray* resultPoints
```
2. 
```swift
var resultPoints: [Any]? { get set }
```

## angle

The angle of a barcode. Values range is from 0 to 360.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger angle
```
2. 
```swift
var angle: Int { get set }
```

## moduleSize

The barcode module size (the minimum bar width in pixel).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger moduleSize
```
2. 
```swift
var moduleSize: Int { get set }
```

## pageNumber

The page number the barcode located in. The index is 0-based.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger pageNumber
```
2. 
```swift
var pageNumber: Int { get set }
```

## regionName

The region name the barcode located in.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSString* regionName
```
2. 
```swift
var regionName: String? { get set }
```

## documentName

The document name.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSString* documentName
```
2. 
```swift
var documentName: String? { get set }
```

## resultCoordinateType

The coordinate type.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumResultCoordinateType resultCoordinateType
```
2. 
```swift
var resultCoordinateType: EnumResultCoordinateType { get set }
```

## accompanyingTextBytes

The accompanying text content in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSData* accompanyingTextBytes
```
2. 
```swift
var accompanyingTextBytes: Data? { get set }
```

## confidence

The confidence of the localization result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger confidence
```
2. 
```swift
var confidence: Int { get set }
```

## transformationMatrix

A transformation matrix that can transform the coordinates of the `resultPoints`. The `transformationMatrix` is calculated from the orientation information of the image.

The images that captured by mobile cameras are always 90 degree counterclockwise rotated from what you see. The coordinates of `resultPoints` are based on the **image coordinate system**. You can use the `transformationMatrix` to rotate the resultPoints from the **image coordinate system** to the **real coordinate system**.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic) CGAffineTransform transformationMatrix;
```
2. 
```swift
var transformationMatrix: CGAffineTransform { get set }
```
