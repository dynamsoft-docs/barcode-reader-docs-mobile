---
layout: default-layout
title: DSAztecDetails Class - Dynamsoft Barcode Reader iOS Edition
description: DSAztecDetails class represents a barcode in Aztec format. It inherits from the DSBarcodeDetails class and contains information about the row count, column count, and layer number of the barcode.
keywords: DSAztecDetails, class, api reference, iOS
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSAztecDetails
permalink: /programming/objectivec-swift/api-reference/auxiliary-iAztecDetails.html
---

# DSAztecDetails

The `DSAztecDetails` class represents a barcode in Aztec format. It inherits from the `DSBarcodeDetails` class and contains information about the row count, column count, and layer number of the barcode.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSAztecDetails : DSBarcodeDetails
```
2. 
```swift
class AztecDetails : BarcodeDetails
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`rows`](#rows) | *NSInteger* | The number of rows in the Aztec barcode. |
| [`columns`](#columns) | *NSInteger* | The number of columns in the Aztec barcode. |
| [`layerNumber`](#layernumber) | *NSInteger* | Specifies the layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code. |

## Methods

| Method | Description |
| ------ | ----------- |
| [`initWithAztecDetails`](#initwithaztecdetails) | Initializes a new instance of the DSAztecDetails class with the specified row count, column count, and layer number of the barcode. |

### rows

The number of rows in the Aztec barcode.

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

The number of columns in the Aztec barcode.

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

### layerNumber

Specifies the layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger layerNumber;
```
2. 
```swift
var layerNumber: Int { get }
```

### initWithAztecDetails

Initializes a new instance of the DSAztecDetails class with the specified row count, column count, and layer number of the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype)initWithAztecDetails:(NSInteger)rows
           columns:(NSInteger)columns
       layerNumber:(NSInteger)layerNumber;
```
2. 
```swift
init(rows: Int, columns: Int, layerNumber: Int)
```

**Parameters**

`rows`: The number of rows in the Aztec barcode.

`columns`: The number of columns in the Aztec barcode.

`layerNumber`: Specifies the layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code. A positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code.
