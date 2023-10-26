---
layout: default-layout
title: DSDataMatrixDetails Class - Dynamsoft Barcode Reader iOS Edition
description: DSDataMatrixDetails class represents the details of a DataMatrix barcode. It is derived from the DSBarcodeDetails class and contains various attributes related to the DataMatrix barcode.
keywords: DSDataMatrixDetails, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDataMatrixDetails
permalink: /programming/objectivec-swift/api-reference/auxiliary-iDataMatrixDetails.html
---

# DSDataMatrixDetails

The `DSDataMatrixDetails` class represents a barcode in OneD format. It inherits from the `DSBarcodeDetails` class and contains information about the column count, row count, and data region info.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSDataMatrixDetails : DSBarcodeDetails
```
2. 
```swift
class DataMatrixDetails : BarcodeDetails
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`rows`](#rows) | *NSInteger* | The row count of the barcode. |
| [`columns`](#columns) | *NSInteger* | The column count of the barcode. |
| [`dataRegionRows`](#dataregionrows) | *NSInteger* | The row count of the barcode data region. |
| [`dataRegionColumns`](#dataregioncolumns) | *NSInteger* | The column count of the barcode data region. |
| [`dataRegionNumber`](#dataregionnumber) | *NSInteger* | The data region count. |

### rows

The row count of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger rows;
```
2. 
```swift
var rows: Int { get }
```

### columns

The column count of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger columns;
```
2. 
```swift
var columns: Int { get }
```

### dataRegionRows

The row count of the barcode data region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger dataRegionRows;
```
2. 
```swift
var dataRegionRows: Int { get }
```

### dataRegionColumns

The column count of the barcode data region.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger dataRegionColumns;
```
2. 
```swift
var dataRegionColumns: Int { get }
```

### dataRegionNumber

The data region count.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger dataRegionNumber;
```
2. 
```swift
var dataRegionNumber: Int { get }
```
