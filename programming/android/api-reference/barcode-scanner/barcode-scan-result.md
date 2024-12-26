---
layout: default-layout
title: BarcodeScanResult Class - Dynamsoft Barcode Scanner Android Edition
description: BarcodeScanResult of DynamsoftBarcodeScanner Android is a result class that contains all decoded barcodes from one scan and the additional information.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScanResult
---

# BarcodeScanResult

`BarcodeScanResult` is a result class that contains all decoded barcodes from one scan and the additional information.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.aar

*Namespace:* com.dynamsoft.dbrbundle.ui

```java
class BarcodeScanResult
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getBarcodes`](#getbarcodes) | Returns an array of `BarcodeResultItem`, which is the basic item of the captured results. |
| [`getResultStatus`](#getresultstatus) | Get the status of the result, which can be finished, canceled or exception. |
| [`getErrorCode`](#geterrorcode) | Returns the error code should something go wrong during the barcode recognition process. |
| [`getErrorString`](#geterrorstring) | Returns the error message associated with the error code should something go wrong during the barcode recognition process. |

### getBarcodes

Returns an array of `BarcodeResultItem`, which is the basic item of the captured results.

```java
BarcodeResultItem[] getBarcodes();
```

**Return Value**

An array of `BarcodeResultItems`. Each `BarcodeResultItem` corresponds to a single barcode.

### getResultStatus

Get the status of the result, which can be finished, canceled or exception.

```java
@EnumResultStatus
int getResultStatus();
```

**Return Value**

The status of the barcode result.

- `RS_FINISHED`: The barcode scanning is finished.
- `RS_CANCELED`: The barcode scanning activity is closed before the process is finished.
- `RS_EXCEPTION`: Failed to start barcode scanning or an error occurs when scanning the barcodes.

### getErrorCode

Returns the error code should something go wrong during the barcode recognition process.

```java
int getErrorCode();
```

**Return Value**

An integer representing a `EnumErrorCode`.

### getErrorString

Returns the error message associated with the error code should something go wrong during the barcode recognition process.

```java
String getErrorString();
```

**Return Value**

A string representing the message of a `EnumErrorCode`.
