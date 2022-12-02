---
layout: default-layout
title: Dynamsoft Barcode Reader Objective-C & Swift API Reference - iDataMatrixDetails Class
description: This page shows the iDataMatrixDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iDataMatrixDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iDataMatrixDetails.html
---


# Class iDataMatrixDetails

`iDataMatrixDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the DataMatrix code details.

```objc
@interface iDataMatrixDetails
```  

| Attribute | Type | Descriptions |
|---------- |-----|------|
| [`moduleSize`](#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | *NSInteger* | The row count of the barcode. |
| [`columns`](#columns) | *NSInteger* | The column count of the barcode. |
| [`dataRegionRows`](#dataregionrows) | *NSInteger* | The data region row count of the barcode. |
| [`dataRegionColumns`](#dataregioncolumns) | *NSInteger* | The data region column count of the barcode. |
| [`dataRegionNumber`](#dataregionnumber) | *NSInteger* | The data region count. |

## moduleSize

The barcode module size (the minimum bar width in pixel).

```objc
@property (nonatomic, assign) NSInteger moduleSize
```

## rows

The row count of the barcode.

```objc
@property (nonatomic, assign) NSInteger rows
```

## columns

The column count of the barcode.

```objc
@property (nonatomic, assign) NSInteger columns
```

## dataRegionRows

The data region row count of the barcode.

```objc
@property (nonatomic, assign) NSInteger dataRegionRows
```

## dataRegionColumns

The data region column count of the barcode.

```objc
@property (nonatomic, assign) NSInteger dataRegionColumns
```

## dataRegionNumber

The data region count.

```objc
@property (nonatomic, assign) NSInteger dataRegionNumber
```
