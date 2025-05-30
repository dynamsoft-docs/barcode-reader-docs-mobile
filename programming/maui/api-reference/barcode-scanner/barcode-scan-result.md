---
layout: default-layout
title: BarcodeScanResult Class - Dynamsoft Barcode Reader MAUI Edition
description: BarcodeScanResult of Dynamsoft Barcode Reader MAUI is a result class that contains all the decoded barcodes.
keywords: barcode, scanner, scan result
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScanResult
---

# BarcodeScanResult

`BarcodeScanResult` is a result class that contains all the decoded barcodes.

## Definition

*Assembly:* Dynamsoft.BarcodeReaderBundle.Maui

*Namespace:* Dynamsoft.BarcodeReaderBundle.Maui

```csharp
class BarcodeScanResult
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`Barcodes`](#barcodes) | [*BarcodeResultItem[]*](../barcode-result-item.md) | Represents all the decoded barcodes in an array of [`BarcodeResultItem`](../barcode-result-item.md). |
| [`ResultStatus`](#resultstatus) | [*EnumResultStatus*](result-status.md) | Represents the result status, which can be finished, canceled or exception. |
| [`ErrorCode`](#errorcode) | *int* | Represents the error code should something go wrong during the barcode scanning process. |
| [`ErrorString`](#errorstring) | *string* | Represents the error message associated with the error code should something go wrong during the barcode scanning process. |

### Barcodes

Represents all the decoded barcodes in an array of [`BarcodeResultItem`](../barcode-result-item.md).

```csharp
BarcodeResultItem[]? Barcodes {get; set;}
```

**See also**

- [`BarcodeResultItem`](../barcode-result-item.md).

### ResultStatus

Represents the status of the result, which can be finished, canceled or exception.

```csharp
EnumResultStatus ResultStatus {get; set;};
```

- `Finished`: The barcode scanning is finished.
- `Canceled`: The barcode scanning activity is closed before the process is finished.
- `Exception`: Failed to start barcode scanning or an error occurs when scanning the barcode.

### ErrorCode

Represents the error code should something go wrong during the barcode scanning process.

```csharp
int ErrorCode {get; set;};
```

### ErrorString

Represents the error message associated with the error code should something go wrong during the barcode scanning process.

```csharp
string? ErrorString {get; set;};
```
