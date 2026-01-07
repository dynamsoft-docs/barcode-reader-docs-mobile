---
layout: default-layout
title: DataMatrixDetails Class - Dynamsoft Barcode Reader Android Edition
description: DataMatrixDetails class of Dynamsoft Barcode Reader Android represents the details of a DataMatrix barcode. It is derived from the BarcodeDetails class and contains various attributes related to the DataMatrix barcode.
keywords: DataMatrixDetails, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DataMatrixDetails
permalink: /programming/android/api-reference/auxiliary-DataMatrixDetails.html
---

# DataMatrixDetails

`DataMatrixDetails` extends the [`DSBarcodeDetails`](barcode-details.md) class and represents detailed information about a Data Matrix barcode.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.aar

*Namespace:* com.dynamsoft.dbr

```java
class DataMatrixDetails extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getRows`](#getrows) | Returns the number of rows of the Data Matrix barcode. |
| [`getColumns`](#getcolumns) | Returns the number of columns of the Data Matrix barcode. |
| [`getDataRegionRows`](#getdataregionrows) | Returns the number of rows in the data region of the Data Matrix barcode. |
| [`getDataRegionColumns`](#getdataregioncolumns) | Returns the number of columns in the data region of the Data Matrix barcode. |
| [`getDataRegionNumber`](#getdataregionnumber) | Returns the number of data regions in the Data Matrix barcode. |

### getRows

Returns the number of rows of the Data Matrix barcode, indicating how many rows of data modules it contains.

```java
int getRows();
```

**Return Value**

An integer representing the row count of the Data Matrix barcode.

### getColumns

Returns the number of columns of the Data Matrix barcode, indicating how many columns of data modules it contains.

```java
int getColumns();
```

**Return Value**

An integer representing the column count of the barcode.

### getDataRegionRows

Returns the number of rows of the data region within the Data Matrix barcode. Data regions are subdivisions of a Data Matrix barcode where data is stored.

```java
int getDataRegionRows();
```

**Return Value**

An integer representing the row count of the barcode data region.

### getDataRegionColumns

Returns the number of columns of the data region within the Data Matrix barcode. Data regions are subdivisions of the barcode where data is stored.

```java
int getDataRegionColumns();
```

**Return Value**

An integer representing the column count of the barcode data region.

### getDataRegionNumber

Returns the number of data regions in the Data Matrix barcode. Data Matrix barcodes can have multiple data regions for storing data redundantly or for error correction purposes.

```java
int getDataRegionNumber();
```

**Return Value**

An ineger representing the data region count.
