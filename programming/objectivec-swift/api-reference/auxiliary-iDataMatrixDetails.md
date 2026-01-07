---
layout: default-layout
title: DSDataMatrixDetails Class - Dynamsoft Barcode Reader iOS Edition
description: DSDataMatrixDetails class of Dynamsoft Barcode Reader iOS represents the details of a DataMatrix barcode. It is derived from the DSBarcodeDetails class and contains various attributes related to the DataMatrix barcode.
keywords: DSDataMatrixDetails, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDataMatrixDetails
permalink: /programming/objectivec-swift/api-reference/auxiliary-iDataMatrixDetails.html
---

# DSDataMatrixDetails

`DSDataMatrixDetails` extends the  [`DSBarcodeDetails`](barcode-details.md) class and represents detailed information about a Data Matrix barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`rows`](#rows) | *NSInteger* | The number of rows of the Data Matrix barcode. |
| [`columns`](#columns) | *NSInteger* | The number of columns of the Data Matrix barcode. |
| [`dataRegionRows`](#dataregionrows) | *NSInteger* | The number of rows in the data region of the Data Matrix barcode. |
| [`dataRegionColumns`](#dataregioncolumns) | *NSInteger* | The number of columns in the data region of the Data Matrix barcode. |
| [`dataRegionNumber`](#dataregionnumber) | *NSInteger* | The number of data regions in the Data Matrix barcode. |

### rows

The number of rows of the Data Matrix barcode, indicating how many rows of data modules it contains.

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

The number of columns of the Data Matrix barcode, indicating how many columns of data modules it contains.

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

The number of rows of the data region within the Data Matrix barcode. Data regions are subdivisions of a Data Matrix barcode where data is stored.

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

The number of columns of the data region within the Data Matrix barcode. Data regions are subdivisions of a Data Matrix barcode where data is stored.

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

The number of data regions in the Data Matrix barcode. Data Matrix barcodes can have multiple data regions for storing data redundantly or for error correction purposes.

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
