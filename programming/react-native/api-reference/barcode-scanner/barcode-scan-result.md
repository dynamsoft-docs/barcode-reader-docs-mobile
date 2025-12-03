---
layout: default-layout
title: BarcodeScanResult Class - Dynamsoft Barcode Reader React Native Edition
description: BarcodeScanResult of Dynamsoft Barcode Reader React Native is a result class that contains all the decoded barcodes.
keywords: barcode, scanner, scan result
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScanResult
---

# BarcodeScanResult

`BarcodeScanResult` is a result class that contains all the decoded barcodes and their associated info.

## Definition   

*Assembly:* dynamsoft-barcode-reader-bundle-flutter


```js
class BarcodeScanResult
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`barcodes`](#barcodes) | *List\<BarcodeResultItem\>* | Represents all the decoded barcodes in a list of [`BarcodeResultItem`](../barcode-reader/barcode-result-item.md). |
| [`status`](#status) | [*EnumResultStatus*](enum/result-status.md) | Represents the result status, which can be finished, canceled or exception. |
| [`errorCode`](#errorcode) | *int* | Represents the error code should something go wrong during the barcode scanning process. |
| [`errorString`](#errorstring) | *string* | Represents the error message associated with the error code should something go wrong during the barcode scanning process. |

### barcodes

Represents all the decoded barcodes in an array of [`BarcodeResultItem`](../barcode-reader/barcode-result-item.md).

```js
barcodes?: BarcodeResultItem[]
```

**Remarks**

Each individual decoded barcode comes out as a [`BarcodeResultItem`](../barcode-reader/barcode-result-item.md), which is part of the Foundational Capture Vision API.

### status

Represents the status of the result, which can be finished, canceled or exception.

```js
resultStatus: EnumResultStatus
```

**Remarks**

- `RS_FINISHED`: The barcode scanning is finished.
- `RS_CANCELED`: The barcode scanning activity is closed before the process is finished.
- `RS_EXCEPTION`: Failed to start barcode scanning or an error occurs during the scanning process.

### errorCode

Represents the error code should something go wrong during the barcode scanning process. In this case, the result status is `RS_EXCEPTION`.

```js
errorCode?: number
```

### errorString

Represents the error message associated with the error code should something go wrong during the barcode scanning process. In this case, the result status is `RS_EXCEPTION`.

```js
errorString?: string
```
