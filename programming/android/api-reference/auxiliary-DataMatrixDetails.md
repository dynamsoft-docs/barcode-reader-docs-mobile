---
layout: default-layout
title: DSDataMatrixDetails Class - Dynamsoft Barcode Reader Android Edition
description: DSDataMatrixDetails class represents the details of a DataMatrix barcode. It is derived from the DSBarcodeDetails class and contains various attributes related to the DataMatrix barcode.
keywords: DSDataMatrixDetails, class, api reference, android
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSDataMatrixDetails
permalink: /programming/android/api-reference/auxiliary-DataMatrixDetails.html
---

# DSDataMatrixDetails

`DataMatrixDetails` is one of the [`detailedResult`](auxiliary-TextResult.md#detailedresult) in class `TextResult`. It stores the DataMatrix code details.

```java
class com.dynamsoft.dbr.DataMatrixDetails;
```

| Attribute | Type | Descriptions |
|---------- | ---- |------|
| [`moduleSize`](#modulesize) | *int* | The barcode module size (the minimum bar width in pixel). |
| [`rows`](#rows) | *int* | The row count of the barcode. |
| [`columns`](#columns) | *int* | The column count of the barcode. |
| [`dataRegionRows`](#dataregionrows) | *int* | The data region row count of the barcode. |
| [`dataRegionColumns`](#dataregioncolumns) | *int* | The data region column count of the barcode. |
| [`dataRegionNumber`](#dataregionnumber) | *int* | The data region count. |

## moduleSize

The barcode module size (the minimum bar width in pixel).

```java
int moduleSize
```

## rows

The row count of the barcode.

```java
int rows
```

## columns

The column count of the barcode.

```java
int columns
```

## dataRegionRows

The data region row count of the barcode.

```java
int dataRegionRows
```

## dataRegionColumns

The data region column count of the barcode.

```java
int dataRegionColumns
```

## dataRegionNumber

The data region count.

```java
int dataRegionNumber
```
