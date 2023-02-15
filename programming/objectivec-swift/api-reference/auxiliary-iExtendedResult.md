---
layout: default-layout
title: iExtendedResult Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iExtendedResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iExtendedResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iExtendedResult.html
---

# Class iExtendedResult

`iExtendedResult` is the extension of the class [`iTextResult`](auxiliary-iTextResult.md). It stores the extended result information.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iExtendedResult: NSObject
```
2. 
```swift
class iExtendedResult: NSObject
```

| Attribute | Type | Descriptions |
|---------- |------|-------------|
| [`resultType`](#resulttype) | [`EnumResultType`]({{ site.mobile_enum }}result-type.html?lang=objc,swift) | The extended result type. |
| [`barcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](#barcodeformat_2) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](#barcodeformatstring) | *NSString \** | Barcode type as string. |
| [`confidence`](#confidence) | *NSInteger* | The confidence of the result. The higher confidence means the higher accuracy. |
| [`bytes`](#bytes) | *NSData \** | The content in a byte array. |
| [`accompanyingTextBytes`](#accompanyingtextbytes) | *NSData \** | The accompanying text content in a byte array. |
| [`accompanyingTextBytesLength`](#accompanyingtextbyteslength) | *NSInteger* | The length of the accompanying text byte array. |
| [`deformation`](#deformation) | *NSInteger* | The deformation value. |
| [`detailedResult`](#detailedresult) | *NSObject \** | One of the following: [`QRCodeDetails`](auxiliary-iQRCodeDetails.md), [`PDF417Details`](auxiliary-iPDF417Details.md), [`DataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`AztecDetails`](auxiliary-iAztecDetails.md), [`OneDCodeDetails`](auxiliary-iOneDCodeDetails.md). |
| [`samplingImage`](#samplingimage) | [`iSamplingImageData*`](auxiliary-iSamplingImageData.md) | The sampling image info. |
| [`clarity`](#clarity) | *NSInteger* | The clarity of the barcode zone in percentage. |

## resultType

Extended result type.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumResultType resultType
```
2. 
```swift
var resultType: EnumResultType { get set }
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
var barcodeFormatString: String { get set }
```

## confidence

The confidence of the result.

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
var barcodeFormatString: Int { get set }
```

## bytes

The content in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSData* bytes
```
2. 
```swift
var bytes: Data? { get set }
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

## accompanyingTextBytesLength

The length of the accompanying text byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSInteger accompanyingTextBytesLength
```
2. 
```swift
var accompanyingTextBytesLength: Int { get set }
```

## deformation

The deformation value.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger deformation
```
2. 
```swift
var deformation: Int { get set }
```

## detailedResult

One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.md), [`iPDF417Details`](auxiliary-iPDF417Details.md), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`iAztecDetails`](auxiliary-iAztecDetails.md), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSObject* detailedResult
```
2. 
```swift
var detailedResult: NSObject? { get set }
```

## samplingImage

The sampling image info.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) iSamplingImageData* samplingImage
```
2. 
```swift
var samplingImage: iSamplingImageData? { get set }
```

## clarity

The clarity of the barcode zone in percentage.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger clarity
```
2. 
```swift
var clarity: Int { get set }
```
