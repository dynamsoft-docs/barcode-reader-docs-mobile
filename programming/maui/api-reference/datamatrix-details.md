---
layout: default-layout
title: DataMatrixDetails Class - Dynamsoft Barcode Reader MAUI Edition
description: DataMatrixDetails class of Dynamsoft Barcode Reader MAUI edition represents the details of a DataMatrix barcode.
keywords: DataMatrixDetails, class, api reference, MAUI
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DataMatrixDetails
---

# DataMatrixDetails

`DataMatrixDetails` represents detailed information about a Data Matrix barcode.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class DataMatrixDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Rows`](#rows) | *int* | The number of rows of the Data Matrix barcode. |
| [`Columns`](#columns) | *int* | The number of columns of the Data Matrix barcode. |
| [`DataRegionRows`](#dataregionrows) | *int* | The number of rows in the data region of the Data Matrix barcode. |
| [`DataRegionColumns`](#dataregioncolumns) | *int* | The number of columns in the data region of the Data Matrix barcode. |
| [`DataRegionNumber`](#dataregionnumber) | *int* | The number of data regions in the Data Matrix barcode. |

### Rows

The number of rows of the Data Matrix barcode, indicating how many rows of data modules it contains.

```csharp
int Rows { get; }
```

### Columns

The number of columns of the Data Matrix barcode, indicating how many columns of data modules it contains.

```csharp
int Columns { get; }
```

### DataRegionRows

The number of rows of the data region within the Data Matrix barcode. Data regions are subdivisions of a Data Matrix barcode where data is stored.

```csharp
int DataRegionRows { get; }
```

### DataRegionColumns

The number of columns of the data region within the Data Matrix barcode. Data regions are subdivisions of the barcode where data is stored.

```csharp
int DataRegionColumns { get; }
```

### DataRegionNumber

The number of data regions in the Data Matrix barcode. Data Matrix barcodes can have multiple data regions for storing data redundantly or for error correction purposes.

```csharp
int DataRegionNumber { get; }
```
