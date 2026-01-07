---
layout: default-layout
title: QRCodeDetails Class - Dynamsoft Barcode Reader MAUI Edition
description: QRCodeDetails class of Dynamsoft Barcode Reader MAUI edition represents the details of a QR Code.
keywords: QRCodeDetails, api reference
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: QRCodeDetails
---

# QRCodeDetails

`QRCodeDetails` represents detailed information specific to a QR Code.

## Definition

*Namespace:* Dynamsoft.BarcodeReader.Maui

*Assembly:* Dynamsoft.BarcodeReader.Maui

```csharp
class QRCodeDetails
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Rows`](#rows) | *int* | The number of rows in the QR Code. |
| [`Columns`](#columns) | *int* | The number of columns in the QR Code. |
| [`ErrorCorrectionLevel`](#errorcorrectionlevel) | *EnumQRCodeErrorCorrectionLevel* | The error correction level of the QR Code.|
| [`Version`](#version) | *int* | The version of the QR Code.|
| [`Model`](#model) | *int* | The number of models of the QR Code.|
| [`Mode`](#mode) | *int* | The first data encoding mode of the QR Code.|
| [`Page`](#page) | *int* | The position of the particular symbol in the structured append format of the QR Code.|
| [`TotalPage`](#totalpage) | *int* | The total number of symbols to be concatenated int the structured append format of the QR Code.|
| [`ParityData`](#paritydata) | *int* | The Parity Data of the QR Code.|
| [`DataMaskPattern`](#datamaskpattern) | *int* | Gets the data mask pattern reference for QR Code symbols. |
| [`Codewords`](#codewords) | *byte[]?* | The codewords of the QR Code. |

### Rows

The number of rows in the QR Code.

```csharp
int Rows { get; }
```

### Columns

The number of columns in the QR Code.

```csharp
int Columns { get; }
```

### ErrorCorrectionLevel

The error correction level of the QR Code as a [`QRCodeErrorCorrectionLevel`]({{site.dbr_maui_api }}enum/qr-code-error-correction-level.html) enumeration item.

```csharp
EnumQRCodeErrorCorrectionLevel ErrorCorrectionLevel { get; }
```

### Version

The version of the QR Code.

```csharp
int Version { get; }
```

### Model

The number of models of the QR Code.

```csharp
int Model { get; }
```

### Mode

The first data encoding mode used in the QR Code.

```csharp
int Mode { get; }
```

### Page

The position of the particular symbol in the structured append format of the QR Code.

```csharp
int Page { get; }
```

### TotalPage

The total number of symbols to be concatenated into the Structured Append format of the QR Code.

```csharp
int TotalPage { get; }
```

### ParityData

The parity data which is obtained by XORing a byte with the ASCII/JIS values of all the original input data before division into symbol blocks.

```csharp
byte ParityData { get; }
```

### DataMaskPattern

Gets the data mask pattern reference for QR Code symbols.

```csharp
int DataMaskPattern { get; }
```

### Codewords

The codewords of the QR Code.

```csharp
byte[]? Codewords { get; }
```
