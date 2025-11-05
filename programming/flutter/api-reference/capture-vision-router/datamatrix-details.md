---
layout: default-layout
title: DataMatrixDetails Class - Dynamsoft Capture Vision Flutter
description: DataMatrixDetails class of DCV Flutter represents the extended info of a DataMatrix Code.
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

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class DataMatrixDetails
```

## Properties

### rows

Represents the number of rows that make up the DataMatrix Code. 

```dart
int rows;
```

### columns

Represents the number of columns that make up the DataMatrix Code.

```dart
int columns;
```

### dataRegionRows

Represents the number of rows in the data region of the DataMatrix code.

```dart
int dataRegionRows;
```

**Remarks**

The data region of a DataMatrix code defines the grid of square/rectangular modules that make up the L-shaped finder pattern as well as the timing pattern which dictates the alternation between the light and dark modules.

### dataRegionColumns

Represents the number of columns in the data region of the DataMatrix code.

```dart
int dataRegionColumns;
```

**Remarks**

The data region of a DataMatrix code defines the grid of square/rectangular modules that make up the L-shaped finder pattern as well as the timing pattern which dictates the alternation between the light and dark modules.

### dataRegionNumber

Represents the number of data regions in the DataMatrix code.

```dart
int dataRegionNumber;
```

**Remarks**

This property is mainly useful when it comes to large DataMatrix codes. Large DataMatrix codes have a grid that is subdivided into multiple data regions, each with its own finder pattern. For smaller DataMatrix codes, there is typically just a single data region.

