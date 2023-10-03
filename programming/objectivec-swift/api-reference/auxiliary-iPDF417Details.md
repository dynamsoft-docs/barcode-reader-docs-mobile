---
layout: default-layout
title: DSPDF417Details Class - Dynamsoft Barcode Reader iOS Edition
description: The DSPDF417Details class represents a barcode in PDF417 format. It inherits from the DSBarcodeDetails class and contains information about the row count, column count, and error correction level of the barcode.
keywords: DSPDF417Details, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSPDF417Details
permalink: /programming/objectivec-swift/api-reference/auxiliary-PDF417Details.html
---

# DSPDF417Details

The `DSPDF417Details` class represents a barcode in PDF417 format. It inherits from the `DSBarcodeDetails` class and contains information about the row count, column count, and error correction level of the barcode.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSPDF417Details : DSBarcodeDetails
```
2. 
```swift
class PDF417Details : BarcodeDetails
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`rows`](#rows) | *NSInteger* | The number of rows in the PDF417 barcode. |
| [`columns`](#columns) | *NSInteger* | The number of columns in the PDF417 barcode. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *NSInteger* | Specifies the error correction level of PDF417 code. |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | *NSInteger* |Represents whether the left row indicator of the PDF417 code exists. If 1, has left row indicator. if 0, don't have left row indicator. |
| [`hasRightRowIndicator`](#hasrightrowindicator) | *NSInteger* |Represents whether the PDF417 barcode has the right row indicator. If 1, has left row indicator. If 0, don't have left row indicator. |

### rows

The number of rows in the PDF417 barcode.

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

The number of columns in the PDF417 barcode.

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

### errorCorrectionLevel

Specifies the error correction level of PDF417 code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger errorCorrectionLevel;
```
2. 
```swift
var errorCorrectionLevel: Int { get }
```

### hasLeftRowIndicator

Represents whether the left row indicator of the PDF417 code exists. If 1, has left row indicator. if 0, don't have left row indicator.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger hasLeftRowIndicator;
```
2. 
```swift
var hasLeftRowIndicator: Int { get }
```

### hasRightRowIndicator

Represents whether the PDF417 barcode has the right row indicator. If 1, has left row indicator. If 0, don't have left row indicator.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) NSInteger hasRightRowIndicator;
```
2. 
```swift
var hasRightRowIndicator: Int { get }
```
