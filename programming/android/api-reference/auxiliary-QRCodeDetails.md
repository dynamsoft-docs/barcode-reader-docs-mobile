---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Barcode Reader Android Edition
description: QRCodeDetails class of Dynamsoft Barcode Reader Android represents the details of a QR Code. It is derived from the BarcodeDetails class and contains various attributes related to the QR Code.
keywords: QRCodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: QRCodeDetails
---

# QRCodeDetails

`QRCodeDetails` extends the [`BarcodeDetails`](barcode-details.md) class and represents detailed information specific to a QR Code.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr

```java
class QRCodeDetails extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getRows`](#getrows) | Returns the number of rows in the QR Code. |
| [`getColumns`](#getcolumns) | Returns the number of columns in the QR Code. |
| [`getErrorCorrectionLevel`](#geterrorcorrectionlevel) | Returns the error correction level of the QR Code.|
| [`getVersion`](#getversion) | Returns the version of the QR Code.|
| [`getModel`](#getmodel) | Returns the number of models of the QR Code.|
| [`getMode`](#getmode) | Returns the first data encoding mode of the QR Code.|
| [`getPage`](#getpage) | Returns the position of the particular symbol in the structured append format of the QR Code.|
| [`getTotalPage`](#gettotalpage) | Returns the total number of symbols to be concatenated int the structured append format of the QR Code.|
| [`getParityData`](#getparitydata) | Returns the Parity Data of the QR Code.|
| [`getDataMaskPattern`](#getdatamaskpattern) | Gets the data mask pattern reference for QR Code symbols. |
| [`getCodewords`](#getcodewords) | Gets the codewords of the QR Code. |

### getRows

Returns the number of rows in the QR Code.

```java
int getRows()
```

**Return Value**

An integer representing the row count of the QR Code.

### getColumns

Returns the number of columns in the QR Code.

```java
int getColumns()
```

**Return Value**

An integer representing the column count of the QR Code.

### getErrorCorrectionLevel

Returns the error correction level of the QR Code as a [`QRCodeErrorCorrectionLevel`]({{site.dbr_android_api }}enum/qr-code-error-correction-level.html?lang=android) enumeration item.

```java
int getErrorCorrectionLevel()
```

**Return Value**

An integer representing the error correction level of the QR Code.

### getVersion

Returns the version of the QR Code.

```java
int getVersion()
```

**Return Value**

An integer representing the version of the QR Code.

### getModel

Returns the number of models of the QR Code.

```java
int getModel()
```

**Return Value**

An integer representing the number of models of the QR Code.

### getMode

Returns the first data encoding mode used in the QR Code.

```java
int getMode()
```

**Return Value**

An integer representing the first data encoding mode of the QR Code.

### getPage

Returns the position of the particular symbol in the structured append format of the QR Code.

```java
int getPage()
```

**Return Value**

An integer representing the position of the particular symbol in the Structured Append format of the QR Code.

### getTotalPage

Returns the total number of symbols to be concatenated into the Structured Append format of the QR Code.

```java
int getTotalPage()
```

**Return Value**

An integer representing the total number of symbols to be concatenated into the Structured Append format of the QR Code.

### getParityData

Returns the parity data which is obtained by XORing a byte with the ASCII/JIS values of all the original input data before division into symbol blocks.

```java
byte getParityData()
```

**Return Value**

A `Byte` object representing the parity data of the QR Code.

### getDataMaskPattern

Gets the data mask pattern reference for QR Code symbols.

```java
int getDataMaskPattern();
```

**Return Value**

The data mask pattern reference for QR Code symbols, of type `int`.

### getCodewords

Gets the codewords of the QR Code.

```java
byte[] getCodewords();
```

**Return Value**

The codewords of the QR Code, of type `byte[]`.
