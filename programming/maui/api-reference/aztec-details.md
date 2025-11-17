---
layout: default-layout
title: AztecDetails Class - Dynamsoft Barcode Reader MAUI Edition
description: AztecDetails class of Dynamsoft Barcode Reader MAUI edition represents a barcode in Aztec format.
keywords: AztecDetails, class, api reference, MAUI
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: AztecDetails
---

# AztecDetails

`AztecDetails` represents details specific to an Aztec barcode.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class AztecDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Rows`](#rows) | *int* | The number of rows of the Aztec barcode. |
| [`Columns`](#columns) | *int* | The number of columns in the Aztec barcode. |
| [`LayerNumber`](#layernumber) | *int* | The layer number of the Aztec barcode. |

### Rows

The number of rows of the Aztec barcode, indicating how many rows of modules it contains.

```csharp
int Rows { get; }
```

### Columns

The number of columns in the Aztec barcode, indicating how many columns of modules it contains.

```csharp
int Columns { get; }
```

### LayerNumber

The layer number of the Aztec barcode. A negative number (-1, -2, -3, -4) specifies a compact Aztec code, while a positive number (1, 2, .. 32) specifies a normal (full-range) Aztec code. The layer number determines the complexity and capacity of the Aztec barcode.

```csharp
int LayerNumber { get; }
```
