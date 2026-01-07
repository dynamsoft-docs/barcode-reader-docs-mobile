---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader Android Edition
description: The PDF417Details class of Dynamsoft Barcode Reader Android represents a barcode in PDF417 format. It inherits from the BarcodeDetails class and contains information about the row count, column count, and error correction level of the barcode.
keywords: PDF417Details, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: PDF417Details
permalink: /programming/android/api-reference/auxiliary-PDF417Details.html
---

# PDF417Details

`PDF417Details` extends the [`BarcodeDetails`](barcode-details.md) class and represents detailed information specific to a PDF417 barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr

```java
class PDF417Details extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getRows`](#getrows) | Returns the number of rows in the PDF417 barcode. |
| [`getCodewords`](#getcodewords) | Returns the code words of the PDF417 barcode. |
| [`getColumns`](#getcolumns) | Returns the number of columns in the PDF417 barcode. |
| [`getErrorCorrectionLevel`](#geterrorcorrectionlevel) | Returns the error correction level of PDF417 code. |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | Indicates whether the left row indicator of the PDF417 code exists. |
| [`hasRightRowIndicator`](#hasrightrowindicator) | Indicates whether the right row indicator of the PDF417 code exists. |

### getRows

Returns the number of rows in the PDF417 barcode, indicating how many rows of modules it contains.

```java
int getRows();
```

**Return Value**

An integer representing the number of rows in the PDF417 barcode.

### getCodewords

Returns the code words of the PDF417 barcode.

```java
int[] getCodewords();
```

**Return Value**

An array of bytes representing the code words of the PDF417 barcode.

### getColumns

Returns the number of columns in the PDF417 barcode, indicating how many columns of modules it contains.

```java
int getColumns();
```

**Return Value**

An integer representing the number of columns in the PDF417 barcode.

### getErrorCorrectionLevel

Returns the error correction level of the PDF417 code.

```java
int getErrorCorrectionLevel();
```

**Return Value**

An integer representing the error correction level of PDF417 code.

### hasLeftRowIndicator

Indicates whether the left row indicator of the PDF417 code exists. If the value is `true`, the PDF417 barcode has the left row indicator. Otherwise, it does not have the left row indicator. The left row indicator is used to denote the start of a new row in the barcode.

```java
boolean hasLeftRowIndicator();
```

**Return Value**

If true, the barcode has the left row indicator. If false, it doesn't have the left row indicator.

### hasRightRowIndicator

Indicates whether the right row indicator of the PDF417 code exists. If the value is `true`, the PDF417 barcode has the right row indicator. Otherwise, it does not have the right row indicator. The right row indicator is used to denote the end of a row in the barcode.

```java
boolean hasRightRowIndicator();
```

**Return Value**

If true, the barcode has the right row indicator. If false, it doesn't have the right row indicator.
