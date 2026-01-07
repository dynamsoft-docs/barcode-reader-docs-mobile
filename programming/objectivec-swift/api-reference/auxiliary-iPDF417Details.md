---
layout: default-layout
title: DSPDF417Details Class - Dynamsoft Barcode Reader iOS Edition
description: The DSPDF417Details class of Dynamsoft Barcode Reader iOS represents a barcode in PDF417 format. It inherits from the DSBarcodeDetails class and contains information about the row count, column count, and error correction level of the barcode.
keywords: DSPDF417Details, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSPDF417Details
permalink: /programming/objectivec-swift/api-reference/auxiliary-iPDF417Details.html
---

# DSPDF417Details

`DSPDF417Details` extends the [`DSBarcodeDetails`](barcode-details.md) class and represents detailed information specific to a PDF417 barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

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
| [`codewords`](#columns) | *NSArray<NSNumber\*> \** | The codewords of the PDF417 barcode. |
| [`columns`](#columns) | *NSInteger* | The number of columns in the PDF417 barcode. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *NSInteger* | The error correction level of PDF417 code. |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | *BOOL* |Indicates whether the left row indicator of the PDF417 code exists. |
| [`hasRightRowIndicator`](#hasrightrowindicator) | *BOOL* |Indicates whether the PDF417 barcode has the right row indicator. |

### rows

The number of rows in the PDF417 barcode, indicating how many rows of modules it contains.

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

### codewords

The codewords of the PDF417 barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, copy, nullable) NSArray<NSNumber *> *codewords;
```
2. 
```swift
var codewords: [NSNumber]? { get }
```

### columns

The number of columns in the PDF417 barcode, indicating how many columns of modules it contains.

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

The error correction level of the PDF417 code.

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

Indicates whether the left row indicator of the PDF417 code exists. If the value is 1, the PDF417 barcode has the left row indicator. Otherwise, it does not have the left row indicator. The left row indicator is used to denote the start of a new row in the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) BOOL hasLeftRowIndicator;
```
2. 
```swift
var hasLeftRowIndicator: Bool { get }
```

### hasRightRowIndicator

Indicates whether the right row indicator of the PDF417 code exists. If the value is 1, the PDF417 barcode has the right row indicator. Otherwise, it does not have the right row indicator. The right row indicator is used to denote the end of a row in the barcode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign, readonly) BOOL hasRightRowIndicator;
```
2. 
```swift
var hasRightRowIndicator: Bool { get }
```
