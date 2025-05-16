---
layout: default-layout
title: BarcodeScanResult Class - Dynamsoft Barcode Reader Android Edition
description: BarcodeScanResult of Dynamsoft Barcode Reader Android is a result class of BarcodeScanner component that contains all decoded barcodes from one scan and the additional information.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScanResult
---

# BarcodeScanResult

`BarcodeScanResult` is a result class that contains all decoded barcodes and their associated info from a single scan.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.aar

*Namespace:* com.dynamsoft.dbrbundle.ui

```java
class BarcodeScanResult
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getBarcodes`](#getbarcodes) | Returns an array of [`BarcodeResultItem`]({{ site.dbr_android_api }}barcode-result-item.html), which represents a single barocde result. |
| [`getResultStatus`](#getresultstatus) | Returns the status of the `BarcodeScanResult`, which can indicate success or failure. |
| [`getErrorCode`](#geterrorcode) | Returns the error code should something go wrong during the barcode recognition process. |
| [`getErrorString`](#geterrorstring) | Returns the error message associated with the error code should something go wrong during the barcode recognition process. |

### getBarcodes

Returns an array of [`BarcodeResultItem`]({{ site.dbr_android_api }}barcode-result-item.html), which represents a single barocde result and is the most basic unit of the captured results.

```java
BarcodeResultItem[] getBarcodes();
```

**Return Value**

An array of [`BarcodeResultItems`]({{ site.dbr_android_api }}barcode-result-item.html). Each [`BarcodeResultItem`]({{ site.dbr_android_api }}barcode-result-item.html) corresponds to a single barcode.

### getResultStatus

Returns the status of the `BarcodeScanResult`, which can be one of *finished*, *canceled* or *exception*.

```java
@EnumResultStatus
int getResultStatus();
```

**Return Value**

The status of the barcode result, of type [EnumResultStatus](enum-result-status.md).

- `RS_FINISHED`: The barcode scanning is finished.
- `RS_CANCELED`: The barcode scanning activity is closed before the process is finished.
- `RS_EXCEPTION`: Failed to start barcode scanning or an error occurs when scanning the barcodes.

### getErrorCode

Returns the error code should something go wrong during the barcode recognition process.

```java
int getErrorCode();
```

**Return Value**

An integer representing a [`EnumErrorCode`]({{ site.dcvb_android_api }}core/enum//error-code.html?lang=android).

### getErrorString

Returns the error message associated with the error code should something go wrong during the barcode recognition process.

```java
String getErrorString();
```

**Return Value**

A string representing the message of a [`EnumErrorCode`]({{ site.dcvb_android_api }}core/enum//error-code.html?lang=android).
