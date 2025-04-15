---
layout: default-layout
title: DSResultStatus - Dynamsoft Barcode Reader iOS Edition
description: DSResultStatus of Dynamsoft Barcode Reader iOS is an enumeration class that defines the result status of the BarcodeScanResult.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSResultStatus
---

# DSResultStatus

`DSResultStatus` is an enumeration class that defines the result status of the `BarcodeScanResult`.

If the status is **finished**, that indicates that the result has been decoded and is available - while **canceled** indicates that the operation has been halted. If the result status is **exception**, then that means that an error has occurred during the barcode detection process.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
typedef NS_ENUM(NSInteger, DSResultStatus)
{
   /* The barcode scanning is finished. You can get at least one result from the BarcodeScanResult.*/
   DSResultStatusFinished = 0
   /* The barcode scanning activity is closed before the process is finished. No results are available.*/
   DSResultStatusCanceled = 1
   /* Failed to start barcode scanning or an error occurs when scanning the barcodes. No results are available.*/
   DSResultStatusException = 2
};
```
1. 
```swift
@objc public enum ResultStatus: Int {
   /* The barcode scanning is finished. You can get at least one result from the BarcodeScanResult.*/
   case finished = 0
   /* The barcode scanning activity is closed before the process is finished. No results are available.*/
   case canceled = 1
   /* Failed to start barcode scanning or an error occurs when scanning the barcodes. No results are available.*/
   case exception = 2
}
```
