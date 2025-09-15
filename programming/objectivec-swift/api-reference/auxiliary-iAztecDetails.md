---
layout: default-layout
title: iAztecDetails Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iAztecDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iAztecDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
---


# Class iAztecDetails

`iAztecDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the Aztec code details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iAztecDetails : NSObject
```
2. 
```swift
class iAztecDetails : NSObject
```

| Attribute | Descriptions |
| --------- | ------------ |
| [`moduleSize`](#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | The row count of the barcode. |
| [`columns`](#columns) | The column count of the barcode. |
| [`layerNumber`](#layernumber) | A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code. |

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

The column count of the barcode.

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

## layerNumber

A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-rang) Aztec code.  

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger layerNumber
```
2. 
```swift
var layerNumber: Int { get set }
```
