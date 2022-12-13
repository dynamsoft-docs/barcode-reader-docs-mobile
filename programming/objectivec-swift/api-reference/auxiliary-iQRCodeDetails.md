---
layout: default-layout
title: iQRCodeDetails Class - Dynamsoft Barcode Reader iOS API Reference
description: This page shows the iQRCodeDetails Class of Dynamsoft Barcode Reader for iOS SDK.
keywords: iQRCodeDetails, class, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
permalink: /programming/objectivec-swift/api-reference/auxiliary-iQRCodeDetails.html
---


# Class iQRCodeDetails

`iQRCodeDetails` is one of the [`detailedResult`](auxiliary-iTextResult.md#detailedresult) in class `iTextResult`. It stores the QRCode details.

```objc
@interface iQRCodeDetails
```  

| Attribute | Type | Descriptions |
|---------- | ---- |-----|
| [`moduleSize`](#modulesize) | *NSInteger* | The barcode module size (the minimum bar width in pixels). |
| [`rows`](#rows) | *NSInteger* | The row count of the barcode.   |
| [`columns`](#columns) | *NSInteger* | The column count of the barcode. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *NSInteger* | The error correction level of the barcode.   |
| [`version`](#version) | *NSInteger* | The version of the QR Code. |
| [`model`](#model) | *NSInteger* | Number of the models. |
| [`mode`](#mode) | *NSInteger* | Identify the first data encoding mode. |
| [`page`](#page) | *NSInteger* | Identify the position of the particular symbol. |
| [`totalPage`](#totalpage) | *NSInteger* | Identify the total number of symbols to be concatenated in the Structured Append format. |
| [`parityData`](#paritydata) | *Byte* | The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks. |

## moduleSize

The barcode module size (the minimum bar width in pixel).  

```objc
@property (nonatomic, assign) NSInteger moduleSize;
```

## rows

The row count of the barcode.  

```objc
@property (nonatomic, assign) NSInteger rows;
```

## columns

The column count of the barcode.

```objc
@property (nonatomic, assign) NSInteger columns;
```

## errorCorrectionLevel

The error correction level of the barcode.

```objc
@property (nonatomic, assign) EnumQRCodeErrorCorrectionLevel errorCorrectionLevel;
```

## version

The version of the QR Code.

```objc
@property (nonatomic, assign) NSInteger version;
```

## model

Number of the models.

```objc
@property (nonatomic, assign) NSInteger model;
```

## mode

Identify the first data encoding mode.

```objc
@property (nonatomic, assign) NSInteger mode;
```

### page

Identify the position of the particular symbol.

```objc
@property (nonatomic, assign) NSInteger page;
```

## totalPage

Identify the total number of symbols to be concatenated in the Structured Append format.

```objc
@property (nonatomic, assign) NSInteger totalPage;
```

## parityData

The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks.

```objc
@property (nonatomic, assign) Byte parityData;
```
