---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader Android Edition
description: The PDF417Details class represents a barcode in PDF417 format. It inherits from the BarcodeDetails class and contains information about the row count, column count, and error correction level of the barcode.
keywords: PDF417Details, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: PDF417Details
permalink: /programming/android/api-reference/auxiliary-PDF417Details.html
---

# PDF417Details

`PDF417Details` class represents detailed information about a PDF417 barcode. It inherits from the [`BarcodeDetails`](barcode-details.md) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class PDF417Details extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`PDF417Details`](#pdf417details-1) | The constructor. Initializes a new instance of the `PDF417Details` class. |
| [`getRows`](#getrows) | Get the number of rows in the PDF417 barcode. |
| [`getColumns`](#getcolumns) | Get the number of columns in the PDF417 barcode. |
| [`getErrorCorrectionLevel`](#geterrorcorrectionlevel) | Get the error correction level of PDF417 code. |
| [`hasLeftRowIndicator`](#hasleftrowindicator) | Represents whether the left row indicator of the PDF417 code exists. |
| [`hasRightRowIndicator`](#hasrightrowindicator) | Represents whether the PDF417 barcode has the right row indicator. |

### PDF417Details

The constructor. Initializes a new instance of the `PDF417Details` class.

```java
PDF417Details();
```

### getRows

Get the number of rows in the PDF417 barcode.

```java
int getRows();
```

**Return Value**

The number of rows in the PDF417 barcode.

### getColumns

Get the number of columns in the PDF417 barcode.

```java
int getColumns();
```

**Return Value**

The number of columns in the PDF417 barcode.

### getErrorCorrectionLevel

Get the error correction level of PDF417 code.

```java
int getErrorCorrectionLevel();
```

**Return Value**

The error correction level of PDF417 code.

### hasLeftRowIndicator

Represents whether the left row indicator of the PDF417 code exists.

```java
boolean hasLeftRowIndicator();
```

**Return Value**

If true, has left row indicator. if false, don't have left row indicator.

### hasRightRowIndicator

Represents whether the PDF417 barcode has the right row indicator.

```java
boolean hasRightRowIndicator();
```

**Return Value**

If true, has right row indicator. If false, don't have right row indicator.
