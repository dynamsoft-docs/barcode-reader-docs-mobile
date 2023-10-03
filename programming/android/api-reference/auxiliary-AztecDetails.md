---
layout: default-layout
title: AztecDetails Class - Dynamsoft Barcode Reader Android Edition
description: AztecDetails class represents a barcode in Aztec format. It inherits from the BarcodeDetails class and contains information about the row count, column count, and layer number of the barcode.
keywords: AztecDetails, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: AztecDetails
permalink: /programming/android/api-reference/auxiliary-AztecDetails.html
---

# AztecDetails

The `AztecDetails` class represents a barcode in Aztec format. It inherits from the [`BarcodeDetails`](barcode-details.md) class and contains information about the row count, column count, and layer number of the barcode.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class AztecDetails extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`AztecDetails`](#aztecdetails) | The constructor. Initializes a new instance of the AztecDetails class. |
| [`getRows`](#getrows) | Gets the number of rows in the Aztec barcode. |
| [`getColumns`](#getcolumns) | Gets the number of columns in the Aztec barcode. |
| [`getLayerNumber`](#getlayernumber) | Gets the layer number of the Aztec barcode. |

### AztecDetails

The constructor. Initializes a new instance of the AztecDetails class.

```java
AztecDetails()
```

### getRows

Gets the number of rows in the Aztec barcode.

```java
int getRows()
```

**Return Value**

The number of rows in the Aztec barcode.

### getColumns

Gets the number of columns in the Aztec barcode.

```java
int getColumns()
```

**Return Value**

The number of columns in the Aztec barcode.

### getLayerNumber

Gets the layer number of the Aztec barcode.

```java
int getLayerNumber()
```

**Return Value**

The layer number of the Aztec barcode.
