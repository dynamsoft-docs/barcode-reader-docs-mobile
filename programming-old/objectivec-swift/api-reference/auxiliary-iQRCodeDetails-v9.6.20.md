---
layout: default-layout
title: iQRCodeDetails Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iQRCodeDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iQRCodeDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iQRCodeDetails-v9.6.20.html
---


# Class iQRCodeDetails

`iQRCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the QRCode details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iQRCodeDetails : NSObject
```
2. 
```swift
class iQRCodeDetails : NSObject
```

| Attribute | Descriptions |
|---------- | ------------ |
| [`moduleSize`](#modulesize) | The barcode module size (the minimum bar width in pixels). |
| [`rows`](#rows) | The row count of the barcode.   |
| [`columns`](#columns) | The column count of the barcode. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | The error correction level of the barcode. |
| [`version`](#version) | The version of the QR Code. |
| [`model`](#model) | Number of the models. |
| [`mode`](#mode) | Identify the first data encoding mode. |
| [`page`](#page) | Identify the position of the particular symbol. |
| [`totalPage`](#totalpage) | Identify the total number of symbols to be concatenated in the Structured Append format. |
| [`parityData`](#paritydata) | The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks. |

## moduleSize

The barcode module size (the minimum bar width in pixel).  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger moduleSize;
```
2. 
```swift
var moduleSize: Int { get set }
```

## rows

The row count of the barcode.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger rows;
```
2. 
```swift
var rows: Int { get set }
```

## columns

The column count of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger columns;
```
2. 
```swift
var columns: Int { get set }
```

## errorCorrectionLevel

The error correction level of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) EnumQRCodeErrorCorrectionLevel errorCorrectionLevel;
```
2. 
```swift
var errorCorrectionLevel: EnumQRCodeErrorCorrectionLevel { get set }
```

## version

The version of the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger version;
```
2. 
```swift
var version: Int { get set }
```

## model

Number of the models.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger model;
```
2. 
```swift
var model: Int { get set }
```

## mode

Identify the first data encoding mode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger mode;
```
2. 
```swift
var mode: Int { get set }
```

### page

Identify the position of the particular symbol.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger page;
```
2. 
```swift
var page: Int { get set }
```

## totalPage

Identify the total number of symbols to be concatenated in the Structured Append format.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger totalPage;
```
2. 
```swift
var totalPage: Int { get set }
```

## parityData

The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) Byte parityData;
```
2. 
```swift
var parityData: Int { get set }
```
