---
layout: default-layout
title: iTextResult Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iTextResult Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iTextResult, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iTextResult.html
---

# Class iTextResult

Stores the text result data.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iTextResult : NSObject
```
2. 
```swift
class iTextResult : NSObject
```

| Attribute | Type | Description |
|-----------|------| ----------- |
| [`barcodeFormat`](#barcodeformat) | [`EnumBarcodeFormat`]({{ site.mobile_enum }}barcode-format.html?lang=objc,swift) | Barcode type in BarcodeFormat group 1. |
| [`barcodeFormat_2`](#barcodeformat_2) | [`EnumBarcodeFormat2`]({{ site.mobile_enum }}barcode-format2.html?lang=objc,swift) | Barcode type in BarcodeFormat group 2. |
| [`barcodeFormatString`](#barcodeformatstring) | *NSString \** | Barcode type as string. |
| [`barcodeText`](#barcodetext) | *NSString \** | The barcode text, ends by '\0'. |
| [`barcodeBytes`](#barcodebytes) | *NSData \** | The barcode content in a byte array. |
| [`localizationResult`](#localizationresult) | [`iLocalizationResult`](auxiliary-iLocalizationResult.md) | The corresponding localization result. |
| [`detailedResult`](#detailedresult) | *NSObject \** | One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.md), [`iPDF417Details`](auxiliary-iPDF417Details.md), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`iAztecDetails`](auxiliary-iAztecDetails.md), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.md). |
| [`extendedResults`](#extendedresults) | [`NSArray<iExtendedResult>`](auxiliary-iExtendedResult.md) | The extended result array. |
| [`exception`](#exception) | *NSString \** | The exception message. |
| [`isDPM`](#isdpm) | *NSInteger* | This attribute stands for whether the result is a DPM result. |
| [`isMirrored`](#ismirrored) | *NSInteger* | This attribute stands for whether the barcode is mirrored. |

## barcodeFormat

Barcode type in BarcodeFormat group 1.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumBarcodeFormat barcodeFormat;
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
@property (nonatomic, assign) EnumBarcodeFormat2 barcodeFormat_2;
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
@property (nonatomic, nullable) NSString* barcodeFormatString;
```
2. 
```swift
var barcodeFormatString: String? { get set }
```

## barcodeText

The barcode text, ends by '\0'.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSString* barcodeText;
```
2. 
```swift
var barcodeText: String? { get set }
```

## barcodeBytes

The barcode content in a byte array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSData* barcodeBytes;
```
2. 
```swift
var barcodeBytes: Data? { get set }
```

## localizationResult

The corresponding localization result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) iLocalizationResult* localizationResult;
```
2. 
```swift
var localizationResult: iLocalizationResult? { get set }
```

## detailedResult

One of the following: [`iQRCodeDetails`](auxiliary-iQRCodeDetails.md), [`iPDF417Details`](auxiliary-iPDF417Details.md), [`iDataMatrixDetails`](auxiliary-iDataMatrixDetails.md), [`iAztecDetails`](auxiliary-iAztecDetails.md), [`iOneDCodeDetails`](auxiliary-iOneDCodeDetails.md).

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSObject* detailedResult;
```
2. 
```swift
var detailedResult: NSObject? { get set }
```

## extendedResults

The extended result array.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSArray<iExtendedResult*>* extendedResults;
```
2. 
```swift
var extendedResults: [iExtendedResult]? { get set }
```

## exception

The exception message.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, nullable) NSString* exception;
```
2. 
```swift
var exception: String? { get set }
```

## isDPM

This attribute stands for whether the result is a DPM result.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger isDPM;
```
2. 
```swift
var isDPM: Int { get set }
```

## isMirrored

This attribute stands for whether the barcode is mirrored.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger isMirrored;
```
2. 
```swift
var isMirrored: Int { get set }
```
