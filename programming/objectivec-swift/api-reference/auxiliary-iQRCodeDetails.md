---
layout: default-layout
title: DSQRCodeDetails Class - Dynamsoft Barcode Reader iOS Edition
description: DSQRCodeDetails class represents the details of a QR Code. It is derived from the DSBarcodeDetails class and contains various attributes related to the QR Code.
keywords: DSQRCodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSQRCodeDetails
permalink: /programming/objectivec-swift/api-reference/auxiliary-QRCodeDetails.html
---

# DSQRCodeDetails

The `DSQRCodeDetails` class represents the details of a QR Code. It is derived from the `DSBarcodeDetails` class and contains various attributes related to the QR Code.

## Definition

*Assembly:* DynamsoftBarcodeReader.framework

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
| [`rows`](#rows) | *NSInteger* | The row count of the QR Code. |
| [`columns`](#columns) | *NSInteger* | The column count of the QR Code. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *DSQRCodeErrorCorrectionLevel* | The error correction level of the QR Code. |
| [`version`](#version) | *NSInteger* | The version of the QR Code. |
| [`model`](#model) | *NSInteger* |Number of models of the QR Code. |
| [`mode`](#mode) | *NSInteger* |Identify the first data encoding mode of the QR Code. |
| [`page`](#page) | *NSInteger* |Identify the position of the particular symbol in the structured append format of the QR Code. |
| [`totalPage`](#totalpage) | *NSInteger* |Identify the total number of symbols to be concatenated int the structured append format of the QR Code. |
| [`parityData`](#paritydata) | *Byte* | The Parity Data shall be an 8 bit byte following the symbol sequence indicator.The parity data is a value obtained by XORing byte by the ASCII/JIS values of all the original input data before division into symbol blocks. |

## Methods

| Method | Description |
| ------ | ----------- |
| [`initWithPDF417Details`](#initwithpdf417details) | Initialize the DSQRCodeDetails object with the specified details. |

### rows

The row count of the QR Code.

### columns

The column count of the QR Code.

### errorCorrectionLevel

The error correction level of the QR Code.

### version

The version of the QR Code.

### model

Number of models of the QR Code.

### mode

Identify the first data encoding mode of the QR Code.

### page

Identify the position of the particular symbol in the structured append format of the QR Code.

### totalPage

Identify the total number of symbols to be concatenated int the structured append format of the QR Code.

### parityData

The Parity Data shall be an 8 bit byte following the symbol sequence indicator.The parity data is a value obtained by XORing byte by the ASCII/JIS values of all the original input data before division into symbol blocks.

### initWithPDF417Details

Initialize the DSQRCodeDetails object with the specified details.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype)initWithPDF417Details:(NSInteger)rows
          columns:(NSInteger)columns
       errorCorrectionLevel:(DSQRCodeErrorCorrectionLevel)errorCorrectionLevel
          version:(NSInteger)version
            model:(NSInteger)model
   mode:(NSInteger)mode
   page:(NSInteger)page
        totalPage:(Byte)totalPage;
```
2. 
```swift
init(rows: Int, columns: Int, errorCorrectionLevel: DSQRCodeErrorCorrectionLevel, version: Int, model: Int, mode: Int, page: Int, totalPage: Byte)
```
