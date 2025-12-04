---
layout: default-layout
title: DataMatrixDetails Class - Dynamsoft Capture Vision React Native
description: DataMatrixDetails class of DCV React Native represents the extended info of a DataMatrix Code.
keywords: datamatrix code, details, result, barcode, extended
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# DataMatrixDetails

The `DataMatrixDetails` class encapsulates all of the extended details of a DataMatrix Code that is not available in the regular barcode result, if the barcode is a DataMatrix Code.

> [!TIP]
> If you would like to learn more about the DataMatrix format, please refer to this [page](https://www.dynamsoft.com/barcode-reader/barcode-types/dataMatrix/).

## Definition

*Assembly:* dynamsoft-capture-vision-react-native

```js
interface DataMatrixDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`rows`](#rows) | *number* | Represents the number of rows that make up the DataMatrix Code. |
| [`columns`](#columns) | *number* | Represents the number of columns that make up the DataMatrix Code. |
| [`dataRegionRows`](#layernumber) | *number* | Represents the number of rows in the data region of the DataMatrix code. |
| [`dataRegionColumns`](#dataregioncolumns) | *number* | Represents the number of columns in the data region of the DataMatrix code. |
| [`dataRegionNumber`](#dataregionnumber) | *number* | Represents the number of data regions in the DataMatrix code. |

### rows

Represents the number of rows that make up the DataMatrix Code. 

```js
rows: number;
```

### columns

Represents the number of columns that make up the DataMatrix Code.

```js
columns: number;
```

### dataRegionRows

Represents the number of rows in the data region of the DataMatrix code.

```js
dataRegionRows: number;
```

**Remarks**

The data region of a DataMatrix code defines the grid of square/rectangular modules that make up the L-shaped finder pattern as well as the timing pattern which dictates the alternation between the light and dark modules.

### dataRegionColumns

Represents the number of columns in the data region of the DataMatrix code.

```js
dataRegionColumns: number;
```

**Remarks**

The data region of a DataMatrix code defines the grid of square/rectangular modules that make up the L-shaped finder pattern as well as the timing pattern which dictates the alternation between the light and dark modules.

### dataRegionNumber

Represents the number of data regions in the DataMatrix code.

```js
dataRegionNumber: number;
```

**Remarks**

This property is mainly useful when it comes to large DataMatrix codes. Large DataMatrix codes have a grid that is subdivided into multiple data regions, each with its own finder pattern. For smaller DataMatrix codes, there is typically just a single data region.

