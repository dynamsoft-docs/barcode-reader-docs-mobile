---
layout: default-layout
title: DSQRCodeDetails Class - Dynamsoft Barcode Reader iOS Edition
description: DSQRCodeDetails class represents the details of a QR Code. It is derived from the DSBarcodeDetails class and contains various attributes related to the QR Code.
keywords: DSQRCodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSQRCodeDetails
permalink: /programming/objectivec-swift/api-reference/auxiliary-iQRCodeDetails.html
---

# DSQRCodeDetails

`DSQRCodeDetails` extends the [`DSBarcodeDetails`](barcode-details.md) class and represents detailed information specific to a QR Code.

## Definition

*Assembly:* DynamsoftBarcodeReader.xcframework

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

### rows

The number of rows in the QR Code.

### columns

The number of columns in the QR Code.

### errorCorrectionLevel

Describes the error correction level of the QR Code as a [`DSQRCodeErrorCorrectionLevel`]({{site.dcv_enumerations}}barcode-reader/qr-code-error-correction-level.html?lang=objc,swift) enumeration item.

### version

The version of the QR Code.

### model

The number of models of the QR Code.

### mode

Identifies the first data encoding mode used in the QR Code.

### page

The position of the particular symbol in the Structured Append format of the QR Code.

### totalPage

The total number of symbols to be concatenated into the Structured Append format of the QR Code.

### parityData

The parity data is obtained by XORing a byte with the ASCII/JIS values of all the original input data before division into symbol blocks. It is used for error checking and correction.