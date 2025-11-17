---
layout: default-layout
title: PDF417Details Class - Dynamsoft Barcode Reader MAUI Edition
description: The PDF417Details class of Dynamsoft Barcode Reader MAUI edition represents a barcode in PDF417 format.
keywords: PDF417Details, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: PDF417Details
---

# PDF417Details

`PDF417Details` represents detailed information specific to a PDF417 barcode.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class PDF417Details
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Rows`](#rows) | *int* | The number of rows in the PDF417 barcode. |
| [`Codewords`](#codewords) | *int[]?* | The code words of the PDF417 barcode. |
| [`Columns`](#columns) | *int* | The number of columns in the PDF417 barcode. |
| [`ErrorCorrectionLevel`](#errorcorrectionlevel) | *int* | The error correction level of PDF417 code. |
| [`HasLeftRowIndicator`](#hasleftrowindicator) | *bool* | Indicates whether the left row indicator of the PDF417 code exists. |
| [`HasRightRowIndicator`](#hasrightrowindicator) | *bool* | Indicates whether the right row indicator of the PDF417 code exists. |

### Rows

The number of rows in the PDF417 barcode, indicating how many rows of modules it contains.

```csharp
int Rows { get; }
```

### Codewords

The code words of the PDF417 barcode.

```csharp
int[]? Codewords { get; }
```

### Columns

The number of columns in the PDF417 barcode, indicating how many columns of modules it contains.

```csharp
int Columns { get; }
```

### ErrorCorrectionLevel

The error correction level of the PDF417 code.

```csharp
int ErrorCorrectionLevel { get; }
```

### HasLeftRowIndicator

Indicates whether the left row indicator of the PDF417 code exists. If the value is `true`, the PDF417 barcode has the left row indicator. Otherwise, it does not have the left row indicator. The left row indicator is used to denote the start of a new row in the barcode.

```csharp
bool hasLeftRowIndicator { get; }
```

### HasRightRowIndicator

Indicates whether the right row indicator of the PDF417 code exists. If the value is `true`, the PDF417 barcode has the right row indicator. Otherwise, it does not have the right row indicator. The right row indicator is used to denote the end of a row in the barcode.

```csharp
bool hasRightRowIndicator { get; }
```
