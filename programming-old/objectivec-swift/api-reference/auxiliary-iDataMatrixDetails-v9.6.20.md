---
layout: default-layout
title: iDataMatrixDetails Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iDataMatrixDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iDataMatrixDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iDataMatrixDetails-v9.6.20.html
---


# Class iDataMatrixDetails

`iDataMatrixDetails` is one of the [`detailedResult`](auxiliary-iTextResult.html#detailedresult) in class `iTextResult`. It stores the DataMatrix code details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface iDataMatrixDetails : NSObject
```
2. 
```swift
class iDataMatrixDetails : NSObject
```

| Attribute | Descriptions |
|---------- |--------------|
| [`moduleSize`](#modulesize) | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | The row count of the barcode. |
| [`columns`](#columns) | The column count of the barcode. |
| [`dataRegionRows`](#dataregionrows) | The data region row count of the barcode. |
| [`dataRegionColumns`](#dataregioncolumns) | The data region column count of the barcode. |
| [`dataRegionNumber`](#dataregionnumber) | The data region count. |

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

## dataRegionRows

The data region row count of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger dataRegionRows
```
2. 
```swift
var dataRegionRows: Int { get set }
```

## dataRegionColumns

The data region column count of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger dataRegionColumns
```
2. 
```swift
var dataRegionColumns: Int { get set }
```

## dataRegionNumber

The data region count.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign) NSInteger dataRegionNumber
```
2. 
```swift
var dataRegionNumber: Int { get set }
```
