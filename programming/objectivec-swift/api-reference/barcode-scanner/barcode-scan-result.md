---
layout: default-layout
title: DSBarcodeScanResult Class - Dynamsoft Barcode Reader iOS Edition
description: DSBarcodeScanResult of Dynamsoft Barcode Reader iOS is a result class of the BarcodeScanner component that contains all decoded barcodes from one scan and the additional information.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSBarcodeScanResult
---

# DSBarcodeScanResult

`DSBarcodeScanResult` is a result class that contains all decoded barcodes and their associated info from a single scan.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSBarcodeScanResult : NSObject
```
2. 
```swift
class BarcodeScanResult : NSObject
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`barcodes`](#barcodes) | *NSArray<DSBarcodeResultItem\*> \** | An array of [`DSBarcodeResultItem`]({{ site.dbr_ios_api }}barcode-result-item.html), which is the basic item of the captured results. |
| [`resultStatus`](#resultstatus) | *DSResultStatus* | The status of the `BarcodeScanResult`, which can indicate success or failure. |
| [`errorCode`](#errorcode) | *NSInteger* | The error code should something go wrong during the barcode recognition process. |
| [`errorString`](#errorstring) | *NSString \** | The error message associated with the error code should something go wrong during the barcode recognition process. |

### barcodes

An array of [`DSBarcodeResultItem`]({{ site.dbr_ios_api }}barcode-result-item.html), which is the basic item of the captured results and is the most basic unit of the captured results.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) NSArray<BarcodeResultItem*>* barcodes;
```
2. 
```swift
var barcodes: [BarcodeResultItem] {get}
```

### resultStatus

The status of the result, which can be one of *finished*, *canceled* or *exception*.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) DSResultStatus resultStatus;
```
2. 
```swift
var resultStatus: ResultStatus {get}
```

**Return Value**

The status of the barcode result, of type [DSResultStatus]({{ site.dbr_ios_api }}barcode-scanner/enum-result-status.html?lang=objc,swift).

- `RS_FINISHED`: The barcode scanning is finished.
- `RS_CANCELED`: The barcode scanning activity is closed before the process is finished.
- `RS_EXCEPTION`: Failed to start barcode scanning or an error occurs when scanning the barcodes.

### errorCode

The error code should something go wrong during the barcode recognition process.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) NSInteger errorCode;
```
2. 
```swift
var errorCode: Int { get }
```

**Return Value**

An integer representing a [`DSError`]({{ site.dcvb_enumerations }}core/error-code.html?lang=objc,swift).

### errorString

The error message associated with the error code should something go wrong during the barcode recognition process.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property (nonatomic, assign, readonly) NSString * errorMessage;
```
2. 
```swift
var errorMessage: String? { get }
```
