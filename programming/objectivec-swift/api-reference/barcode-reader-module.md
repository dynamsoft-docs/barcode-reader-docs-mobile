---
layout: default-layout
title: DSBarcodeReaderModule Class - Dynamsoft Barcode Reader iOS Edition
description: DSBarcodeReaderModule class of Dynamsoft Barcode Reader iOS defines general functions in the barcode reader module.
keywords: barcode reader module, iOS, get version
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSBarcodeReaderModule
permalink: /programming/objectivec-swift/api-reference/barcode-reader-module.html
---

# DSBarcodeReaderModule

The `DSBarcodeReaderModule` class defines general functions in the barcode reader module.

## Definition

*Assembly:* DynamsoftCaptureVisionBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSBarcodeReaderModule : NSObject
```
2. 
```swift
class BarcodeReaderModule : NSObject
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getVersion`](#getversion) | Get the version of Dynamsoft Barcode Reader. |

## getVersion

Get the version of Dynamsoft Barcode Reader.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (NSString *)getVersion;
```
2. 
```swift
class func getVersion() -> String
```

**Return Value**

The version of Dynamsoft Barcode Reader.
