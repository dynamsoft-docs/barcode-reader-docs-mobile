---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Barcode Reader Android Edition
description: QRCodeDetails class represents the details of a QR Code. It is derived from the BarcodeDetails class and contains various attributes related to the QR Code.
keywords: QRCodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: QRCodeDetails
permalink: /programming/android/api-reference/auxiliary-QRCodeDetails.html
---

# QRCodeDetails

`QRCodeDetails` class represents detailed information about a QRCode barcode. It inherits from the [`BarcodeDetails`](barcode-details.md) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class QRCodeDetails extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`QRCodeDetails`](#qrcodedetails-1) | The constructor. Initializes a new instance of the `QRCodeDetails` class. |
| [`getRows`](#getrows) | Get the row count of the QR Code.|
| [`getColumns`](#getcolumns) | Get the column count of the QR Code.|
| [`getErrorCorrectionLevel`](#geterrorcorrectionlevel) | Get the error correction level of the QR Code.|
| [`getVersion`](#getversion) | Get the version of the QR Code.|
| [`getModel`](#getmodel) | Get the number of models of the QR Code.|
| [`getMode`](#getmode) | Get the first data encoding mode of the QR Code.|
| [`getPage`](#getpage) | Get the position of the particular symbol in the structured append format of the QR Code.|
| [`getTotalPage`](#gettotalpage) | Get the total number of symbols to be concatenated int the structured append format of the QR Code.|
| [`getParityData`](#getparitydata) | Get the Parity Data of the QR Code.|

### QRCodeDetails

Initializes a new instance of the QRCodeDetails class.

```java
QRCodeDetails()
```

### getRows

Get the row count of the QR Code.

```java
int getRows()
```

**Return Value**

The row count of the QR Code.

### getColumns

Get the column count of the QR Code.

```java
int getColumns()
```

**Return Value**

The column count of the QR Code.

### getErrorCorrectionLevel

Get the error correction level of the QR Code.

```java
int getErrorCorrectionLevel()
```

**Return Value**

The error correction level of the QR Code.

### getVersion

Get the version of the QR Code.

```java
int getVersion()
```

**Return Value**

The version of the QR Code.

### getModel

Get the number of models of the QR Code.

```java
int getModel()
```

**Return Value**

The number of models of the QR Code.

### getMode

Get the first data encoding mode of the QR Code.

```java
int getMode()
```

**Return Value**

The first data encoding mode of the QR Code.

### getPage

Get the position of the particular symbol in the structured append format of the QR Code.

```java
int getPage()
```

**Return Value**

The position of the particular symbol in the structured append format of the QR Code.

### getTotalPage

Get the total number of symbols to be concatenated int the structured append format of the QR Code.

```java
int getTotalPage()
```

**Return Value**

The total number of symbols to be concatenated int the structured append format of the QR Code.

### getParityData

Get the Parity Data of the QR Code.

```java
byte getParityData()
```

**Return Value**

The Parity Data of the QR Code.
