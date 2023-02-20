---
layout: default-layout
title: iPDF417Details Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iPDF417Details Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iPDF417Details, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iPDF417Details.html
---


# Class iPDF417Details

`iPDF417Details` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the PDF417 code details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iPDF417Details : NSObject
```
2. 
```swift
class iPDF417Details : NSObject
```

| Attribute | Type | Descriptions |
|---------- |------|------------ |
| [`moduleSize`](#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | *NSInteger* | The row count of the barcode. |
| [`columns`](#columns) | *NSInteger* | The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *NSInteger* | The error correction level of the barcode. |
| [`hasLeftRowIndicator`] | *int* | Indicates whether the PDF417 barcode has a left row indicator. |
| [`hasRightRowIndicator`] | *int* | Indicates whether the PDF417 barcode has a right row indicator. |

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

## rows

The row count of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger rows
```
2. 
```swift
var rows: Int { get set }
```

## columns

The column count of codewords between the left and right row indicators, where the actual data and the ECC is encoded.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger columns
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
@property (nonatomic, assign) NSInteger errorCorrectionLevel
```
2. 
```swift
var errorCorrectionLevel: Int { get set }
```

## hasLeftRowIndicator

Indicates whether the PDF417 barcode has a left row indicator.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger hasLeftRowIndicator
```
2. 
```swift
var hasLeftRowIndicator: Int { get set }
```

## hasRightRowIndicator

Indicates whether the PDF417 barcode has a right row indicator.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger hasRightRowIndicator
```
2. 
```swift
var hasRightRowIndicator: Int { get set }
```
