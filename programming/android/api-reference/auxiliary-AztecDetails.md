---
layout: default-layout
title: AztecDetails Class - Dynamsoft Barcode Reader Android Edition
description: AztecDetails class of Dynamsoft Barcode Reader Android represents a barcode in Aztec format. It inherits from the BarcodeDetails class and contains information about the row count, column count, and layer number of the barcode.
keywords: AztecDetails, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: AztecDetails
permalink: /programming/android/api-reference/auxiliary-AztecDetails.html
---

# AztecDetails

`AztecDetails` extends the [`BarcodeDetails`](barcode-details.md) class and represents details specific to an Aztec barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr

```java
class AztecDetails extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getRows`](#getrows) | Returns the number of rows of the Aztec barcode. |
| [`getColumns`](#getcolumns) | Returns the number of columns in the Aztec barcode. |
| [`getLayerNumber`](#getlayernumber) | Returns the layer number of the Aztec barcode. |

### getRows

Returns the number of rows of the Aztec barcode, indicating how many rows of modules it contains.

```java
int getRows()
```

**Return Value**

An integer representing the number of rows in the Aztec barcode.

### getColumns

Returns the number of columns in the Aztec barcode, indicating how many columns of modules it contains.

```java
int getColumns()
```

**Return Value**

An integer representing the number of columns in the Aztec barcode.

### getLayerNumber

Returns the layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code, while a positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code. The layer number determines the complexity and capacity of the Aztec barcode.

```java
int getLayerNumber()
```

**Return Value**

An integer representing the layer number of the Aztec barcode.
