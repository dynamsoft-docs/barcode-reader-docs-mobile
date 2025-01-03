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

`DSResultStatus` is a enumeration class that defines the result status of the `BarcodeScanResult`.

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
    DSResultStatusFinished = 0
    DSResultStatusCanceled = 1
    DSResultStatusException = 2
};
```
2. 
```swift
@objc public enum ResultStatus: Int {
    case finished = 0
    case canceled = 1
    case exception = 2
}
```
