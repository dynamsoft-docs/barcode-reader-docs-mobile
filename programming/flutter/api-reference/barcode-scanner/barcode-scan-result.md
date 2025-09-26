---
layout: default-layout
title: BarcodeScanResult Class - Dynamsoft Barcode Reader Flutter Edition
description: BarcodeScanResult of Dynamsoft Barcode Reader Flutter is a result class that contains all the decoded barcodes.
keywords: barcode, scanner, scan result
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScanResult
---

# BarcodeScanResult

`BarcodeScanResult` is a result class that contains all the decoded barcodes and their associated info.

## Definition   

*Assembly:* dynamsoft-barcode-reader-bundle-flutter


```dart
class BarcodeScanResult
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`barcodes`](#barcodes) | *List\<BarcodeResultItem\>* | Represents all the decoded barcodes in a list of [`BarcodeResultItem`](../capture-vision-router-lite/barcode-result-item.md). |
| [`status`](#status) | [*EnumResultStatus*](../enum/result-status.md) | Represents the result status, which can be finished, canceled or exception. |
| [`errorCode`](#errorcode) | *int* | Represents the error code should something go wrong during the barcode scanning process. |
| [`errorString`](#errorstring) | *string* | Represents the error message associated with the error code should something go wrong during the barcode scanning process. |

### barcodes

Represents all the decoded barcodes in an array of [`BarcodeResultItem`](../capture-vision-router-lite/barcode-result-item.md).

```dart
List<BarcodeResultItem>? barcodes;
```

**Remarks**

Each individual decoded barcode comes out as a [`BarcodeResultItem`](../capture-vision-router-lite/barcode-result-item.md), which is part of the Foundational Capture Vision API.

### status

Represents the status of the result, which can be finished, canceled or exception.

```dart
EnumResultStatus resultStatus;
```

**Remarks**

- `EnumResultStatus.finished`: The barcode scanning is finished.
- `EnumResultStatus.canceled`: The barcode scanning activity is closed before the process is finished.
- `EnumResultStatus.exception`: Failed to start barcode scanning or an error occurs during the scanning process.

### errorCode

Represents the error code should something go wrong during the barcode scanning process. In this case, the result status is `EnumResultStatus.exception`.

```dart
int? errorCode;
```

### errorString

Represents the error message associated with the error code should something go wrong during the barcode scanning process. In this case, the result status is `EnumResultStatus.exception`.

```dart
String? errorString;
```
