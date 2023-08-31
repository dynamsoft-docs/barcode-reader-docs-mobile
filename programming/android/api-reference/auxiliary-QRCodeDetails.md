---
layout: default-layout
title: DSQRCodeDetails Class - Dynamsoft Barcode Reader Android Edition
description: DSQRCodeDetails class represents the details of a QR Code. It is derived from the DSBarcodeDetails class and contains various attributes related to the QR Code.
keywords: DSQRCodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSQRCodeDetails
permalink: /programming/android/api-reference/auxiliary-QRCodeDetails.html
---

# DSQRCodeDetails

The `DSQRCodeDetails` class represents the details of a QR Code. It is derived from the `DSBarcodeDetails` class and contains various attributes related to the QR Code.

```java
class com.dynamsoft.dbr.QRCodeDetails;
```

| Attribute | Type | Descriptions |
|---------- | ---- | ------------ |
| [`moduleSize`](#modulesize) | *int* | The barcode module size (the minimum bar width in pixels). |
| [`rows`](#rows) | *int* | The row count of the barcode.   |
| [`columns`](#columns) | *int* | The column count of the barcode. |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | *int* | The error correction level of the barcode.   |
| [`version`](#version) | *int* | The version of the QR Code. |
| [`model`](#model) | *int* | Number of the models. |
| [`mode`](#mode) | *int* | Identify the first data encoding mode. |
| [`page`](#page) | *int* | Identify the position of the particular symbol. |
| [`totalPage`](#totalpage) | *int* | Identify the total number of symbols to be concatenated in the Structured Append format. |
| [`parityData`](#paritydata) | *byte* | The byte parity data |

## moduleSize

The barcode module size (the minimum bar width in pixels).

```java
int moduleSize
```

## rows

The row count of the barcode.  

```java
int rows
```

## columns

The column count of the barcode.

```java
int columns
```

## errorCorrectionLevel

The error correction level of the barcode.  

```java
int errorCorrectionLevel
```

## version

The version of the QR Code.

```java
int version
```

## model

Number of the models.

```java
int model
```

## mode

Identify the first data encoding mode.

```java
int mode
```

## page

Identify the position of the particular symbol.

```java
int page
```

## totalPage

Identify the total number of symbols to be concatenated in the Structured Append format.

```java
int totalPage
```

## parityData

The Parity Data shall be an 8 bit byte following the Symbol Sequence Indicator. The parity data is a value obtained by XORing byte by byte the ASCII/JIS values of all the original input data before division into symbol blocks.

```java
byte parityData
```
