---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Barcode Reader Android API Reference
description: This page shows the QRCodeDetails Class of Dynamsoft Barcode Reader for Android SDK.
keywords: QRCodeDetails, class, api reference, android
needAutoGenerateSidebar: false
permalink: /programming/android/api-reference/auxiliary-QRCodeDetails-v8.1.0.html
---


# QRCodeDetails

Stores the QRCode details.  

## Attributes
  
| Attribute | Type |
|---------- | ---- |
| [`moduleSize`](#modulesize) | *int* |
| [`rows`](#rows) | *int* |
| [`columns`](#columns) | *int* |
| [`errorCorrectionLevel`](#errorcorrectionlevel) | [`EnumQRCodeErrorCorrectionLevel`]({{ site.mobile_enum }}qr-code-error-correction-level.html?lang=android) |
| [`version`](#version) | *int* |
| [`model`](#model) | *int* |

### moduleSize

The barcode module size (the minimum bar width in pixels).

```java
int com.dynamsoft.dbr.QRCodeDetails.moduleSize
```

### rows

The row count of the barcode.  

```java
int com.dynamsoft.dbr.QRCodeDetails.rows
```

### columns

The column count of the barcode.

```java
int com.dynamsoft.dbr.QRCodeDetails.columns
```

### errorCorrectionLevel

The error correction level of the barcode.  

```java
int com.dynamsoft.dbr.QRCodeDetails.errorCorrectionLevel
```

### version

The version of the QR Code.

```java
int com.dynamsoft.dbr.QRCodeDetails.version
```

### model

Number of the models.

```java
int com.dynamsoft.dbr.QRCodeDetails.model
```
