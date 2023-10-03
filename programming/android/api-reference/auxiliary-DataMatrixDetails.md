---
layout: default-layout
title: DataMatrixDetails Class - Dynamsoft Barcode Reader Android Edition
description: DataMatrixDetails class represents the details of a DataMatrix barcode. It is derived from the BarcodeDetails class and contains various attributes related to the DataMatrix barcode.
keywords: DataMatrixDetails, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DataMatrixDetails
permalink: /programming/android/api-reference/auxiliary-DataMatrixDetails.html
---

# DataMatrixDetails

`DataMatrixDetails` class represents detailed information about a DataMatrix barcode. It inherits from the [`BarcodeDetails`](barcode-details.md) class.

## Definition

*Assembly:* DynamsoftBarcodeReader.aar

*Namespace:* com.dynamsoft.dbr

```java
class DataMatrixDetails extends BarcodeDetails
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`DataMatrixDetails`](#datamatrixdetails-1) | The constructor. Initializes a new instance of the DataMatrixDetails class. |
| [`getRows`](#getrows) | Get the row count of the barcode. |
| [`getColumns`](#getcolumns) | Get the column count of the barcode. |
| [`getDataRegionRows`](#getdataregionrows) | Get the row count of the barcode data region. |
| [`getDataRegionColumns`](#getdataregioncolumns) | Get the column count of the barcode data region. |
| [`getDataRegionNumber`](#getdataregionnumber) | Get the data region count. |

### DataMatrixDetails

The constructor. Initializes a new instance of the DataMatrixDetails class.

```java
DataMatrixDetails();
```

### getRows

Get the row count of the barcode.

```java
int getRows();
```

**Return Value**

The row count of the barcode.

### getColumns

Get the column count of the barcode.

```java
int getColumns();
```

**Return Value**

The column count of the barcode.

### getDataRegionRows

Get the row count of the barcode data region.

```java
int getDataRegionRows();
```

**Return Value**

The row count of the barcode data region.

### getDataRegionColumns

Get the column count of the barcode data region.

```java
int getDataRegionColumns();
```

**Return Value**

The column count of the barcode data region.

### getDataRegionNumber

Get the data region count.

```java
int getDataRegionNumber
```

**Return Value**

The data region count.
