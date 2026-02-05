---
layout: default-layout
title: DSQRCodeDetails Class - Dynamsoft Barcode Reader iOS Edition
description: DSQRCodeDetails class of Dynamsoft Barcode Reader iOS represents the details of a QR Code. It is derived from the DSBarcodeDetails class and contains various attributes related to the QR Code.
keywords: DSQRCodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSQRCodeDetails
---

# DSQRCodeDetails

`DSQRCodeDetails` extends the [`DSBarcodeDetails`](barcode-details.md) class and represents detailed information specific to a QR Code.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NS_SWIFT_NAME(QRCodeDetails)
@interface DSQRCodeDetails : DSBarcodeDetails
```
2. 
```swift
class QRCodeDetails : BarcodeDetails
```

## Attributes

| Attributes | Type | Description |
| ---------- | ---- | ----------- |
| [`rows`](#rows) | *NSInteger* | The number of rows in the QR Code. |
| [`columns`](#columns) | *NSInteger* | The number of columns in the QR Code. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *DSQRCodeErrorCorrectionLevel* | The error correction level of the QR Code. |
| [`version`](#version) | *NSInteger* | The version of the QR Code. |
| [`model`](#model) | *NSInteger* | The number of models of the QR Code. |
| [`mode`](#mode) | *NSInteger* | Identifies the first data encoding mode of the QR Code. |
| [`page`](#page) | *NSInteger* | Identifies the position of the particular symbol in the structured append format of the QR Code. |
| [`totalPage`](#totalpage) | *NSInteger* | The total number of symbols to be concatenated into the Structured Append format of the QR Code. |
| [`parityData`](#paritydata) | *Byte* | The Parity Data of the QR Code. |
| [`dataMaskPattern`](#datamaskpattern) | *NSInteger* | The data mask pattern reference for QR Code symbols. |
| [`codewords`](#codewords) | *NSData \** | The codewords of the QR Code. |

### rows

The number of rows in the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSInteger rows;
```
2. 
```swift
var rows: Int { get }
```

### columns

The number of columns in the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSInteger columns;
```
2. 
```swift
var columns: Int { get }
```

### errorCorrectionLevel

Describes the error correction level of the QR Code as a [`DSQRCodeErrorCorrectionLevel`]({{site.dcvb_enumerations}}barcode-reader/qr-code-error-correction-level.html?lang=objc,swift) enumeration item.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) DSQRCodeErrorCorrectionLevel errorCorrectionLevel;
```
2. 
```swift
var errorCorrectionLevel: QRCodeErrorCorrectionLevel { get }
```

### version

The version of the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSInteger version;
```
2. 
```swift
var version: Int { get }
```

### model

The number of models of the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSInteger model;
```
2. 
```swift
var model: Int { get }
```

### mode

Identifies the first data encoding mode used in the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSInteger mode;
```
2. 
```swift
var mode: Int { get }
```

### page

The position of the particular symbol in the Structured Append format of the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSInteger page;
```
2. 
```swift
var page: Int { get }
```

### totalPage

The total number of symbols to be concatenated into the Structured Append format of the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSInteger totalPage;
```
2. 
```swift
var totalPage: Int { get }
```

### parityData

The parity data is obtained by XORing a byte with the ASCII/JIS values of all the original input data before division into symbol blocks. It is used for error checking and correction.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) Byte parityData;
```
2. 
```swift
var parityData: Int { get }
```

### dataMaskPattern

The data mask pattern reference for QR Code symbols.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, assign) NSInteger dataMaskPattern;
```
2. 
```swift
var dataMaskPattern: Int { get }
```

### codewords

The codewords of the QR Code.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, readonly, copy, nullable) NSData *codewords;
```
2. 
```swift
var codewords: Data? { get }
```
